<template>
    <div class="contact__content">
        <h3 class="contact__title">Un petit message pour en savoir plus ?</h3>

        <form id="form2" method="post" action="form.php" class="contact__form">
            <div class="contact__form-div">
                <label for="nomform" class="contact__form-tag">Nom</label>
                <input name="nom" id="nomform" type="text" placeholder='Votre nom' class="contact__form-input" required>
            </div>

            <div class="contact__form-div">
                <label for="prenomform" class="contact__form-tag">Mail</label>
                <input name="mail" type="email" placeholder="Votre mail" class="contact__form-input" id="prenomform"
                    required>
            </div>

            <div class="contact__form-div contact__form-area">
                <label for="textarea1" class="contact__form-tag">Message</label>
                <textarea name="commentaire" id="textarea1" cols="30" rows="10" placeholder="Votre message"
                    class="contact__form-input" required></textarea>
            </div>

            <input type="submit" class="button form-control submit" value="Envoyer">
        </form>
    </div>
</template>

<style scoped>
.contact__title {
    text-align: center;
    font-size: small;
    margin-bottom: 1.5rem;
}
.contact__form-tag {
    position: absolute;
    top: -.75rem;
    left: 1.25rem;
    font-size: var(--small-font-size);
    padding: .25rem;
    background-color: var(--body-color);
    z-index: 10;
}
.contact__form-div {
    position: relative;
    margin-bottom: 2rem;
    height: 4rem;
}

.contact__form-input {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 2px solid var(--text-color-light);
    background: none;
    color: var(--text-color);
    outline: none;
    padding: 1.5rem;
    border-radius: .75rem;
    z-index: 1;
}
</style>