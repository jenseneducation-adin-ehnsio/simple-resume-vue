<template>
  <div id="app">
    <div class="top">
      <p class="italic">Söker LIA plats med start 16 november 2020 - 7 maj 2021</p>
    </div>
    
    <div class="left">
      <!-- Send object with first and last name, place avatar.jpg in assets  -->
      <NameAndImg :name="name"/>
      <!-- Send object prop with a title and info -->
      <InfoText :info="aboutMe"/>
      
      <!-- Send array of objects with url, relative url to icon and a title -->
      <Socials :socials="socMedia"/>

      <!-- Send array of objects with text and img name -->
      <Contact :contact="contact" />
      
    </div>
    <div class="right">
      <!-- Send object prop with a title and info -->
      <InfoText :info="frontEnd"/>
      <InfoText :info="meAtWork"/>
      <!-- Send string prop for the title and an array of objects with place, title and duration-->
      <List :title="'Arbetserfarenhet'" :list="work" />
      <List :title="'Studier'" :list="education" />
      <!-- Send empty strings on place and duration for single line -->
      <List :title="'Övriga kunskaper'" :list="other" />
    </div>
    
  </div>
  
</template>

<script>
import List from "@/components/List.vue"
import InfoText from "@/components/InfoText.vue"
import NameAndImg from "@/components/NameAndImg.vue"
import Socials from "@/components/Socials.vue"
import Contact from "@/components/Contact.vue"

export default {
  name: 'App',
  components: {
    List, InfoText, NameAndImg, Socials, Contact
  },
  data() {return{
    // Name
    name: { first: "Adin", last: "Ehnsiö"},
    // List of exp
    work: [
      { place: "Epidemic Sound", title: "Musikproducent", duration: "2020 - nu"},
      { place: "PostNord Sverige", title: "Brevbärare/Chaufför", duration: "2016 - 2019"},
      { place: "UNICEF", title: "Administration/Kundtjänst", duration: "2013 - 2015"},
      { place: "UNICEF", title: "Fundraiser", duration: "2013 - 2015"},
      { place: "Oslo Kommun", title: "Förskoleassistent", duration: "2013 - 2015"},
    ],
    education: [
      { place: "Jensen Education YH", title: "Front end developer", duration: "2019 - 2021"},
      { place: "Södertörns högskola", title: "Statsvetenskap", duration: "2018 - 2019"},
      { place: "Studio Blue", title: "Ljudteknik/Musikproduktion", duration: "2013 - 2015"},
    ],
    other: [
      { place: "", title: "Språkkunnig (Svenska, Engelska, Norska)", duration: ""},
      { place: "", title: "Körkort B", duration: ""},
    ],
    // Text sections
    frontEnd: {title: "Front End", info: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."},
    meAtWork: {title: "Jag på jobbet", info: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."},
    aboutMe: {title: "Om mig", info: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur."},
    //Social media links, place img in assets and change imgSrc to name of the file 
    socMedia: [
      { title: "linkedin", url: "https://www.linkedin.com/in/adin-ehnsi%C3%B6-0aa1661a4/", imgSrc: 'linkedin.svg'},
      { title: "github", url: "https://www.github.com", imgSrc: 'github.svg'},
    ],
    //Place icons in assets and change imgSrc to name of the file
    contact: [
      { title: "076 - 2621733", imgSrc: 'phone.png'},
      { title: "adinehnsio@gmail.com", imgSrc: 'mail.png'},
    ]
  }}
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat&display=swap');
$green: rgb(16, 114, 53);

.green {
  color: $green;
  font-weight: 600;
}
h1, h2, h3, h4 {
  margin: 10px
}
h4 {
  font-size: 1.1em;
}
h1, h2, h3 {
  font-weight: 100;
}
h1 {
  font-size: 1.8em;
  margin: 20px;
  text-align: left;
  letter-spacing: 1px;
}
p {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 1.1em;
}
.border {
  border: 2px black solid;
  padding: 10px;
}
body {
  margin: auto;
  max-width: 1400px;
}
.italic {
  font-style: italic;
}
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
#app {
  transition: all 1s ease-in-out;
  margin: 0 5vw 40px 5vw;
  font-family: 'Montserrat', sans-serif;  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  grid-template-columns: 1fr 2fr;
  grid-template-areas: auto;
  grid-template-areas: 
    "top top"
    "left right";
  display: grid;
  justify-items: center;
  
  .right {
    width: 100%;
    border: 1px solid black;
    grid-area: right;
    p, h1, h2, h3, h4 {
      padding: 0 80px 0 80px;
    }
    h4{
      margin-top: 30px;
    }
  }
  .top {
    grid-area: top;
  }
  .left {
    border: 1px solid black;
    min-width: 260px;
    padding: 20px 20px 50px 20px;
    color: white;
    display: flex;
    flex-direction: column;
    grid-area: left;
    align-items: center;
    background-color: rgb(29, 28, 28);
    border: 1px solid rgb(29, 28, 28);
    img {
      height: 170px;
      width: 170px;
      border-radius: 50%;
      margin: 20px;
    } 
    p {
      padding: 0 25px 0 25px;
    }
    .socials, .contact {
      margin-top: 50px;
      .div {
        display: flex;
        flex-direction: column;
        align-items: center;
        img {
          height: 48px;
          width: 48px;
          filter: brightness(0) invert(1);
          border-radius: 0;
        }
      }
      a {
        img {
          width: 40px;
          height: 40px;
        }
      }
    }
    .socials {
      display: flex;
      img {
        margin-bottom: 0;
      }
      a {
        text-decoration: none;
        color: white;
      }
      p {
        margin: 5px;
        font-size: 10px;
      }
    }
  }
}
@media screen and(max-width: 800px) {
  #app {
    margin: 0 0 40px 0;
    grid-template-areas: 
    "top top"
    "left left"
    "right right";
  .left, .right {
    border: none;
  }
  }
}

@media screen and(max-width: 1000px) {
  #app {
    margin: 0 0 40px 0;
    .right {
      border-right: none;
      border-left: none;
      p, h1, h2, h3, h4 {
        padding: 0;
      }
    .info-text {
      padding: 0 50px 0 50px
    }
    }
  }
}

</style>
