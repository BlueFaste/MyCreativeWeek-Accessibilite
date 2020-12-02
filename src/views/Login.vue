<template>
  <div> 

  <nav aria-label="Breadcrumb" class="breadcrumb">
    <ul>
        <li><a href="">Accueil</a></li>
        <li><span aria-current="page">Connexion</span></li>
    </ul>
  </nav>
    
  <h1>Connectez-vous à votre compte MyDigitalSchool</h1>
  
  <div class="connexion">
    <p>Email : <input type="email" class="email" placeholder="Entrez votre email.."></p><br>
    <p>Mot de passe : <input type="password" class="mdp" placeholder="Entrez votre mot de passe.."></p>
    <p class="forget">Mot de passe oublié ?</p>
  </div>
  <input type="submit" class="valider" value="Valider">

</div>
</template>

<script>
export default {
  name: "Login"
}
</script>

<style scoped>

.breadcrumb ul {
    display: flex;
    list-style-type: none;
}
    
.breadcrumb li::before {
    content: "→ ";
}
    
.breadcrumb li:first-child::before {
    content: "";
}

h1{
  font-family: Ubuntu Mono;
  font-size: 1.5rem;
  color: #393939;
}

p{
  font-family: Helvetica Neue;
  color: #393939;
}

.connexion{
  margin-top: 4rem;
  margin-left: auto;
  margin-bottom: 2rem;
  margin-right: auto;
    width: 18.3rem;
    height: 8.5rem;
}

.email{
  width: 15rem;
  height: 2rem;
  font-size: 0.7rem;
  border-color: #C9C9C9;
}

.mdp{
   width: 11.3rem;
  height: 2rem;
  font-size: 0.7rem;
  border-color: #C9C9C9;
}

.forget{
  margin-top: -0.8rem;
  font-size: 0.7rem;
  text-align: right;
}
.valider{
  border: none;
  width:5rem;
  font-family: Ubuntu Mono;
}
</style>
