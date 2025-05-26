<template>
  <div class="h-full w-full max-w-2xl mx-auto">
    <form @submit.prevent="handleSubmit" class="w-full bg-white/10 rounded border border-[#6DA48F] shadow-inner shadow-white/10 p-6 sm:p-8 h-full flex flex-col">
      <div class="w-full max-w-xl mx-auto flex-1 flex flex-col justify-center">

        <div class="mb-5">
          <input
              type="text"
              id="name"
              v-model="formData.name"
              required
              placeholder="Nom*"
              class="w-full p-3 border border-white/20 rounded bg-white/10 text-white placeholder-white/70 focus:outline-none focus:border-white/50 transition-colors"
          >
        </div>

        <div class="mb-5">
          <input
              type="email"
              id="email"
              v-model="formData.email"
              required
              placeholder="E-mail*"
              class="w-full p-3 border border-white/20 rounded bg-white/10 text-white placeholder-white/70 focus:outline-none focus:border-white/50 transition-colors"
          >
        </div>

        <div class="mb-5">
          <input
              type="tel"
              id="phone"
              v-model="formData.phone"
              required
              placeholder="Telephone*"
              class="w-full p-3 border border-white/20 rounded bg-white/10 text-white placeholder-white/70 focus:outline-none focus:border-white/50 transition-colors"
          >
        </div>

        <button
            type="submit"
            class="w-full p-3 bg-[#6DA48F] border border-white/20 shadow-lg rounded text-black cursor-pointer transition-all duration-500 ease-in-out text-2xl font-medium hover:bg-[#D4B48C] hover:scale-105"
        >
          Rappellez-moi !
        </button>

      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'ContactFormLite',
  data() {
    return {
      formData: {
        name: '',
        email: '',
        phone: ''
      }
    }
  },
  methods: {
    async handleSubmit() {
      try {
        // Vérification des required
        if (!this.formData.name || !this.formData.email || !this.formData.phone) {
          alert('Veuillez remplir tous les champs obligatoires');
          return;
        }

        const formData = new FormData();

        formData.append('access_key', 'cc706538-1781-4f64-be1b-374cddd8512d');
        formData.append('from_name', this.formData.name);
        formData.append('email', this.formData.email);
        formData.append('subject', `Site OJ-Debarras: Demande de Rappel de ${this.formData.name} - ${this.formData.phone}`);
        formData.append('message', `Bonjour, J'aurais besoin de renseignements pour un débarras.\nNuméro de téléphone : ${this.formData.phone}`);

        console.log('Envoi des données...', Object.fromEntries(formData));

        const response = await fetch('https://api.web3forms.com/submit', {
          method: 'POST',
          body: formData
        });

        const data = await response.json();
        console.log('Réponse:', data);

        if (data.success) {
          alert('Message envoyé avec succès!');
          this.formData = {
            name: '',
            phone: '',
            email: ''
          };
        } else {
          alert("Erreur lors de l'envoi : " + (data.message || 'Veuillez réessayer.'));
          console.error(data.message);
        }
      } catch (error) {
        console.error('Erreur détaillée:', error);
        alert('Une erreur est survenue lors de l\'envoi du message. Veuillez réessayer.');
      }
    }
  }
}
</script>