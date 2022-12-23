<template>
    <header>
        <nav>
            <div id="navPages">
                <div class="navPlacer">
                    <router-link to="/"><i class="fa-solid fa-dice-d6"></i> </router-link>     
                    <router-link to="/">Accueil</router-link> 
                    <router-link to="/portfolio">Portfolio</router-link> 
                    <router-link to="/skills">Compétences</router-link>
                    <router-link to="/contact">Contact</router-link>
                </div>
            </div>
    
            <div id="navSocial">
                <div class="navPlacer">
                    <a href=""><i class="fa-brands fa-linkedin"></i></a>
                    <a href="https://www.youtube.com/channel/UC3bdjwFyOP8P31ZV9NW8EVQ" target="blank"><i class="fa-brands fa-youtube"></i></a>
                </div>      
            </div>
        </nav>
    </header>   
</template>

<style>
    header{
        height:100px;
        height:auto;
   
    }
    nav{
        display:flex;
    
        height:100px;
        margin:0 auto;
        justify-content: space-between;
        padding:1em 5em;
      
        
    }

    nav figcaption i{font-size:4em; margin-top:0.2em;}

    nav #navPages, nav #navSocial{
        display:flex;
        flex-direction: column;
        justify-content: center;
    }

    #navPages a{
        margin-right:15px;
   
    }

    #navSocial a i{
        font-size:18px;
        margin: 0 0.25em;
    }

    .fa-youtube:hover{
        color:red !important;
    }


    nav figcaption a {
        margin:0;
    }

</style>