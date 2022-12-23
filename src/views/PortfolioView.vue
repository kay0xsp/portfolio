<template>
  
  <div>
    <aside>
        <v-breadcrumbs
        v-if="!modalActivator"
          :items="items"
          divider="/"
        ></v-breadcrumbs>
      </aside>
      <section>
    
    <div id="MyModal" class="animate pop" v-if="modalActivator">  
      <button @click="modalActivator = false"><i class="fa-solid fa-circle-xmark"></i></button>
        <div class="modalBoxPortfolio">
            <figcaption>
              <img :src="`${publicPath}` + portfolioTemp[3]" alt="" />
            </figcaption>
            <div class="modalBoxPortfolioDescription">
              <strong>{{portfolioTemp[1]}}</strong>
              <p>{{portfolioTemp[2]}}</p>
              <a :href="portfolioTemp[4]" target="blank">{{ portfolioTemp[5] }} <i class="fa-solid fa-link"></i></a>
            </div>
        </div>
    </div>

    <ul id="portfolio" v-if="!modalActivator">
        <li
         v-for="p in portfolioList" 
         :key="p.id"
         @click="modalActivation(p.id, p.name, p.description, p.picturePath, p.link, p.linkName)"
         class="animated glow"
         :class="p.cssAttribute"
         >
          <img :src="`${publicPath}` + p.vignettePicture" alt="" />
          <i class="fa-solid fa-arrow-up-right-from-square"></i>
        </li>
    </ul> 
</section>
  </div>
 
      
</template>
<script>
  import { mapState } from 'vuex';
  import portfolio from '../json/portfolio.json';
  export default {
    data () {
      return {
        publicPath: process.env.BASE_URL,
        portfolioList : portfolio,
        modalActivator: false,
        items: [
            {
              text: 'IronKy',
              disabled: false,
              href: '/',
            },
            {
              text: 'Portfolio',
              disabled: true
            }
          ]
      }
    },
    methods:{
    modalActivation(id, name, description, picture, link, linkName){
        this.modalActivator = true;

      this.portfolioTemp.splice("");
      const index = id;
      const modalName = name;
      const desc = description;
      const image = picture;
      const modalLink = link;
      const linkTitle = linkName;

      this.portfolioTemp.push(
        index,
        modalName,
        desc,
        image,
        modalLink,
        linkTitle
      );
      }
    },
    computed:{
      ...mapState({
        portfolioTemp: (state) => state.portfolioTemp,
    })
    }
  }
</script>
<style>
.modalBoxPortfolio{
  width:auto;
  height:100%;
  margin:10px 0 0 0 ;
}

.animate.pop {
  animation-duration: 0.5s;
  animation-name: animate-pop;
  animation-timing-function: cubic-bezier(.26, .53, .74, 1.48);
}

@keyframes animate-pop {
  0% {
    opacity: 0;
    transform: scale(0.5, 0.5);
  }

  100% {
    opacity: 1;
    transform: scale(1, 1);
  }
}

.animated {
  animation-duration: 0.55s;
  animation-delay: 0.10s;
  animation-name: animate-fade;
  animation-timing-function: cubic-bezier(0.26, 0.53, 0.74, 1.48);
  animation-fill-mode: backwards;
}

/* Glow In */
.animated.glow {
  animation-name: animate-glow;
  animation-timing-function: ease;
}

@keyframes animate-glow {
  0% {
    opacity: 0;
    filter: brightness(3) saturate(3);
    transform: scale(0.8, 0.8);
  }
  100% {
    opacity: 1;
    filter: brightness(1) saturate(1);
    transform: scale(1, 1);
  }
}

.delay-1 { animation-delay: 0.1s; }  
.delay-2 { animation-delay: 0.15s; }
.delay-3 { animation-delay: 0.2s; }
.delay-4 { animation-delay: 0.25s; }
.delay-5 { animation-delay: 0.3s; }
.delay-6 { animation-delay: 0.35s; }

.modalBoxPortfolio{
  display:flex;
}

.modalBoxPortfolio figcaption{
  width:70%;
  height:90%;
  background-color: black;
  overflow: hidden;
}

.modalBoxPortfolio figcaption img{
  width:100%;
  height:100%;
  object-fit: cover;
}

.modalBoxPortfolio .modalBoxPortfolioDescription{
  margin-top:10px;
  margin-left:25px;
}

.modalBoxPortfolioDescription a{
  background-color: black;
  display:block;
  width:200px;
  padding-top:15px;
  height:50px;
  text-align: center;
  color:white;
  font-weight:bold;
  text-transform: uppercase;
  vertical-align: center;
  border-radius:0.25em;
  transition:0.5s;
}

.modalBoxPortfolioDescription a:hover{
  background-color: #218fd8;
}

.modalBoxPortfolioDescription strong{
  font-size:3em;
}

.modalBoxPortfolioDescription p {max-width: 450px; margin:1em 0; font-size:1.2em; line-height:1.2em}

#MyModal{
  position:fixed;
  width:96%;
  height:80%;
  z-index:100;
  margin:0 2em;
  border:1px solid #218fd8;
  border-radius:0.5em;
  background-color: white;
  padding:2em;
}


#portfolio{
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
}

#portfolio i{
  position:absolute;
  color:#218fd8;
  margin-left:-35px;
  margin-top:15px;
  font-size:1.5em;
}

#portfolio li{
    min-width:550px;
    border-radius:0.5em;
    overflow: hidden;
    height:300px;
    margin:20px 10px;
    background-color: rgb(148, 148, 148);
    border:1px solid rgb(224, 224, 224);
    cursor:pointer;
    transition:0.5s !important;
}

#portfolio li:hover{
  transition:1s !important;
  box-shadow: rgba(0, 0, 0, 0.17) 0px -23px 25px 0px inset, rgba(0, 0, 0, 0.15) 0px -36px 30px 0px inset, rgba(0, 0, 0, 0.1) 0px -79px 40px 0px inset, rgba(0, 0, 0, 0.06) 0px 2px 1px, rgba(0, 0, 0, 0.09) 0px 4px 2px, rgba(0, 0, 0, 0.09) 0px 8px 4px, rgba(0, 0, 0, 0.09) 0px 16px 8px, rgba(0, 0, 0, 0.09) 0px 32px 16px;
}

.fa-circle-xmark{
  color:red !important;
  font-size:1.5em;
}

#portfolio li img{
  width:100%;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
}

</style>