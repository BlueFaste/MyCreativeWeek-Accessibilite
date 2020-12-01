<template>
  <footer class="footer d-flex justify-content-around align-items-center">
    <div>
      <div class="d-flex footerText text-left ubuntu-B row p-4 justify-content-between">
        <ul class="col footerLink">
          <li><router-link to="/"> Accueil </router-link></li>
          <li><router-link to="/login"> Connexion </router-link></li>
          <li><router-link to=""> Ajouter un projet </router-link></li>
        </ul>
        <ul class="col footerLink">
          <li><a href="https://www.mydigitalschool.com/" title="MyDigitalSchool - nouvel onglet" target="_blank">MyDigitalSchool</a></li>
        </ul>
        <div class="d-flex flex-column footerLink col">
          <label for="newsletter">Inscrivez-vous à notre <span lang="en">Newsletter</span></label>
          <form action="" method="post" class="d-flex">
            <input type="email" id="newsletter" placeholder="Email"/>
            <b-button class="buttonMDS buttonNwlt">Valider</b-button>
          </form>
        </div>
      </div>
      <p id="mentionLegal" class="ubuntu-B">© 2020 My Digital School - Tous droits réservés | Mentions légales</p>

    </div>
    <ul>
      <li class="my-3"><img src="../assets/imgs/Rs/Facebook.png" alt="Facebook de MyDigitalSchool" class="w-75"/></li>
      <li class="my-3"><img src="../assets/imgs/Rs/Instagram.png" alt="Instagram de MyDigitalSchool" class="w-75"/></li>
      <li class="my-3"><img src="../assets/imgs/Rs/Youtube.png" alt="Youtube de MyDigitalSchool" class="w-75"/></li>
      <li class="my-3"><img src="../assets/imgs/Rs/Twitter.png" alt="Twitter de MyDigitalSchool" class="w-75"/></li>
      <li class="my-3"><img src="../assets/imgs/Rs/LinkedIn.png" alt="LinkedIn de MyDigitalSchool" class="w-75"/></li>
    </ul>

  </footer>
</template>

<script>
export default {
  name: "Footer"
}
</script>

<style scoped>
.footer {
  background-color: black;
  opacity: 80%;
  /*padding: 2rem 12rem;*/
  padding: 1rem 0;
  position: relative;
}

.buttonNwlt {
  margin: 0;
}

.footerText {
  color: white;
  opacity: 80%;
}

ul {
  list-style: none;
}

.footerLink {
  width: 15rem;
}
li a {
  color: white;
}

ul li, label {
  margin-bottom: 1rem;
}

#mentionLegal{
  /*align-self: flex-end;*/
  position: absolute;
  left: 33%;
  color: white;
  opacity: 80%;
}

</style>
