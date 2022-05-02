<script setup>
</script>

<template>

    <div id="mainDiv">
        <div class="list">
            <ul>
                <li @click="showInfo" id="0">Platon Anton</li>
                <li @click="showInfo" id="1">Darie Cristian</li>
                <li @click="showInfo" id="2">Nosferatu Vladimir</li>
                <li @click="showInfo" id="3">Parker Peter</li>
                <li @click="showInfo" id="4">Samurai Jack</li>
            </ul>
        </div>
        <div id="info">

        </div>
        
    </div>
    

</template>

<script>
export default ({
    data() {
      return {       
        persons : [
            {
                Name : "Anton",
                Surname : "Platon",
                Age : 17,
                Ocupation : "Student in College",
                Email : "antuankovaliski@gmail.com"
            },
            {
                Name : "Cristian",
                Surname : "Darie",
                Age : 20,
                Ocupation : "Freelancer, Student",
                Email : "Belii0in0MD@gmail.com"
            },
            {
                Name : "Vladimir",
                Surname : "Nosferatu",
                Age : 18,
                Ocupation : "Dracula, Problem-maker",
                Email : "alwayshere@gmail.com"
            },
            {
                Name : "Peter",
                Surname : "Parker",
                Age : 36,
                Ocupation : "SuperHero, Actor",
                Email : "Spoodyman@gmail.com"
            },
            {
                Name : "Jack",
                Surname : "Samurai",
                Age : 56,
                Ocupation : "Teacher of Martial arts",
                email : "somethinglikekatana@gmail.com"
            }
        ]
      }  
    },
    methods: {
        showInfo(event){
            let leftDiv = document.getElementById("info");
            leftDiv.innerHTML = "";
            for (const key in this.persons) {
                if (key == event.target.id) {
                    for (const par in this.persons[key]) {
                        console.log(par," : ",this.persons[key][par]);
                        let textInfo = document.createElement("p");
                        textInfo.textContent = `${par} : ${this.persons[key][par]}`;
                        leftDiv.appendChild(textInfo);
                    }                  
                }
            }
        }    
    },
    computed: {
    
    }
})
</script>

<style>
@import '@/assets/base.css';


header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }

 

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }


}


li{
    list-style: none;
}
input{
    width: 100px;
}
#mainDiv{
    display: flex;
    width: 100%;
    justify-content: space-around;
    align-items: center;
}
#info{
  margin:60px
}

</style>
