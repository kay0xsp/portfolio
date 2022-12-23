<template>
    <div>
      <aside>
        <v-breadcrumbs
        
          :items="items"
          divider="/"
        ></v-breadcrumbs>
      </aside>
      <div id="skills">
          <article>
            <strong>FRONTEND</strong>
            <ul class="dashboard-front">
              <li v-for="f in frontendList" :key="f.id">
                <svg>
                  <circle class="bg" cx="57" cy="57" r="52" />
                  <circle :class="f.cssAttribute" cx="57" cy="57" r="52" />
                </svg>
                <b><i v-if="f.brandAttribute" :class="f.brandAttribute"></i> {{ f.name }}</b>
              </li>
            </ul>
          </article>
          <article>
            <strong>BACKEND</strong>
            <ul class="dashboard-front">
              <li v-for="f in backendList" :key="f.id">
                <svg>
                  <circle class="bg" cx="57" cy="57" r="52" />
                  <circle :class="f.cssAttribute" cx="57" cy="57" r="52" />
                </svg>
                <b><i v-if="f.brandAttribute" :class="f.brandAttribute"></i> {{ f.name }}</b>
              </li>
            </ul>
          </article>
          <article>
            <strong>CMS</strong>
            <ul class="dashboard-front">
              <li v-for="f in miscList" :key="f.id">
                <svg>
                  <circle class="bg" cx="57" cy="57" r="52" />
                  <circle :class="f.cssAttribute" cx="57" cy="57" r="52" />
                </svg>
                <b><i v-if="f.brandAttribute" :class="f.brandAttribute"></i> {{ f.name }}</b>
              </li>
            </ul>
          </article>
          <article>
            <strong>PROGRAMMES</strong>
            <ul class="dashboard-front">
              <li v-for="f in programmList" :key="f.id">
                <svg>
                  <circle class="bg" cx="57" cy="57" r="52" />
                  <circle :class="f.cssAttribute" cx="57" cy="57" r="52" />
                </svg>
                <b><i v-if="f.brandAttribute" :class="f.brandAttribute"></i> {{ f.name }}</b>
              </li>
            </ul>
          </article>
      </div>
    </div>
    
 
  </template>

  <script>
  import frontend from '../json/frontend.json';
  import backend from '../json/backend.json';
  import programm from '../json/programm.json';
  import misc from '../json/misc.json';

  export default{
      data(){
        return{
          backendList : backend,
          frontendList :frontend,
          miscList: misc,
          programmList: programm,
          items: [
            {
              text: 'IronKy',
              disabled: false,
              href: '/',
            },
            {
              text: 'Compétences',
              disabled: true
            }
          ]
        }
      }
  }
</script>

<style>

#skills{
  display:flex;
  padding:0 5em;
  margin-top:50px;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

#skills article{
  border:1px solid #218fd8;
  padding:0em 0 3em 0;
  border-radius:0.5em;
  margin-bottom:3em;
}

#skills strong{
  display:block;
  margin-bottom:2em;
  padding: 0.25em 0 0.25em 1em;
  background-color: #218fd8;
  color:white;
  border-top-left-radius: 0.25em 0.25em;
  border-top-right-radius: 0.25em 0.25em;
  border-bottom:1px solid #218fd8;
}

.dashboard-front {
  display: flex;
  width:500px;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

.dashboard-front li{
  text-align: center;
  display:flex;
  flex-direction: column;
}

svg {
  width: 114px;
  height: 114px;
  margin: 1em;
}

.bg {
  fill: none;
  stroke-width: 10px;
  stroke: #1A2C34;
}

[class^="meter-"] {
  fill: none;
  stroke-width: 10px;
  stroke-linecap: round;
  transform: rotate(-90deg);
  transform-origin: 50% 50%;
  
}

.meter-1 {
  stroke-dasharray: 360;
  stroke-dashoffset: 0;
  stroke: #e34c26;
  animation: progress-1 1s ease-out;
}
.meter-2 {
  stroke: #264de4;
  stroke-dasharray: 360;
  stroke-dashoffset: 0;
  animation: progress-1 .75s ease-out;
}
.meter-3 {
  stroke: #41B883;
  stroke-dasharray: 360;
  stroke-dashoffset: 100;
  animation: progress-3 .5s ease-out;
}

.meter-4 {
  stroke: rgb(0, 195, 255);
  stroke-dasharray: 360;
  stroke-dashoffset: 200;
  animation: progress-4 .5s ease-out;
}

.meter-5 {
  stroke: #F0DB4F;
  stroke-dasharray: 360;
  stroke-dashoffset: 120;
  animation: progress-5 .5s ease-out;
}

@keyframes progress-1 {
    from {
        stroke-dashoffset: 360;
    }
    to {
        stroke-dashoffset: 0;
    }
}

@keyframes progress-2 {
  from {
    stroke-dashoffset: 360;
  }
  to {
    stroke-dashoffset: 160;
  }
}

@keyframes progress-3 {
  from {
    stroke-dashoffset: 360;
  }
  to {
    stroke-dashoffset: 100;
  }
}

@keyframes progress-4 {
  from {
    stroke-dashoffset: 360;
  }
  to {
    stroke-dashoffset: 200;
  }
}

@keyframes progress-5 {
  from {
    stroke-dashoffset: 360;
  }
  to {
    stroke-dashoffset: 120;
  }
}

</style>


