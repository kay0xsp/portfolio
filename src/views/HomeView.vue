<template>
  <section>
  <div class="home">
    <article class="animatedDescription">
      <br>
      <strong><i class="fa-solid fa-location-dot"></i>  Toulouse, France</strong>
      <h2>
         <strong> Felicité </strong>   <br> François
      </h2>
      <p>
        Bonjour je m'appelle Felicité François, je suis développeur Full stack exercant depuis + de 4 ans,
        avec une éxperience en UI - UX design. <br>
        J'applique les principes de MVC et POO dans mes projets professionnels.
      </p>
      <b>
        <router-link to="/portfolio">Portfolio</router-link>  <i class="fa-solid fa-arrow-right"></i>
        <router-link to="/skills"> Compétences </router-link> <i class="fa-solid fa-arrow-right"></i>
      </b>
    </article>
 
    <aside>
        <figcaption>
            <img src="../assets/dude.png" alt="">
        </figcaption>
    </aside>
  </div>
  </section>
</template>

<script>
export default {
  name: 'HomeView'
}
</script>

<style>
.home{
  padding:5em 8em;
  display: flex;
  margin: 0 auto;
  justify-content: center;

}

.home article b i{ margin-right:25px;}

.home p{max-width:500px; font-size:1.22em;}

.home article b a{
  transition:0.5s;
}

.home article{margin-right:8em;}

.home article p{
  margin-bottom:15px;
}

.home article b a:hover{
  margin-right:25px;
}


.animatedDescription{
  animation-duration: 0.5s;
  animation-name: animate-slide;
  animation-timing-function: cubic-bezier(.26, .53, .74, 1.48);
}

@keyframes animate-slide {
  0% {
    opacity: 0;
    margin-left:-50px;
  }

  100% {
    opacity: 1;
    margin-left:0;
  }
}

h2{
  font-size:6em;
  text-transform: uppercase;
  margin-bottom:25px;
}

aside{
  max-width:500px;

  border-radius:16em;
}

</style>
