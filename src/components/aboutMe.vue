<template>
  <div v-on:click="hideAbout">
    <button class="close-about" v-on:click="hideAbout">X</button>
    <ul class="about-me">
      <li >
        <img class="me" src="../images/ruthface.png" alt="ruth's face" />
      </li>
      <li>
        <div class="words">
          <h4 class="words2">
            As a <b>software developer</b> with a background in academia, arts,
            and childcare, I am ready to dive into a career in the tech
            industry. I bring strong skills in <b>research</b>,
            <b>communication</b>, and <b>creative thinking</b>.
          </h4>
          <h4 class="words2">
            I am always looking for opportunities to learn and develop, solve
            new problems, and make meaningful contributions to the world.
          </h4>
          <h4 class="words2">
            I have recently completed a intensive 16 week Professional Software
            Development course at CodeClan and I am excited to take my first
            steps into the tech industry.
          </h4>
          <div class="afterwords">
            <h4>
              I have experience working with PYTHON, JAVASCRIPT, JAVA, HTML, CSS
              and VUE, MONGODB, POSTGRESQL, SPRING, REACT, TDD, AGILE.
            </h4>
          </div>
          <div class="afterafterwords">
            <p>
              Please feel free to contact me by
              <a
                href="mailto:ruthlilfoulis@gmail.com"
                target="_blank"
                class="list-item2"
                
              >
                email!
              </a>
            </p>
            <h4>And please explore some of my coding projects below:</h4>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import { eventBus } from "../main.js";
export default {
  methods: {
    hideAbout() {
      eventBus.$emit("about-selected", this.about);
    },
  },
};
</script>

<style>
.close-about {
  font-family: "Montserrat", sans-serif;
  font-size: 14pt;
  background-color: seagreen;
  color: turquoise;
  border-radius: 5px;
  text-align: center;
  align-content: right;
  justify-content: right;
  padding: 1px 1px 1px 1px;
  width: 24px;
}
.close:hover {
  background-color: darkseagreen;
  color: seagreen;
  cursor: pointer;
}

.me {
  background-color: darkseagreen;
  border-radius: 5px;
  max-width: 120px;
  margin: 5px 5px 5px 10px;
  
}

.words {
  justify-content: right;
  margin: 0px 10px 0px 10px;
  max-width: 870px;
  line-height: 1.6;
  border: 3px solid darkseagreen;
  border-radius: 5px;
  padding: 1% 0% 1% 1%;
}

.words2 {
  justify-content: center;
  margin: 0% 0% 0% 1%;
  padding: 1% 0% 1% 1%;
  width: 90%;
  line-height: 1.6;
}

.afterwords {
  justify-content: right;
  justify-self: right;
  align-content: right;
  text-align: right;
  background-color: darkseagreen;
  border-radius: 5px;
  width: 90%;
  color: darkgreen;
  padding: 0px 5px 0px 5px;
  margin: 0px 0px 0px 0px;
}

.afterafterwords {
 
  padding: 0px 0px 0px 0px;
  margin: 0px 0px 0px 0px;
}

.list-item2 {
  font-family: "Montserrat", sans-serif;
  font-size: 12pt;
  background-color: seagreen;
  color: turquoise;
  border-radius: 5px;
  padding: 5px;
  margin: 10px;
  text-align: center;
  text-decoration: none;
}

.list-item2:hover {
  background-color: darkseagreen;
  color: seagreen;
  cursor: pointer;
}


.about-me {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  list-style-type: none;
  align-content:space-around;
  padding: 0% 0% 0% 0%;
  
}
</style>