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
                class="list-item"
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
  padding: 0 0 0 0;
  margin-left: 97%;
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
  align-self: left;
  max-width: 85%;
  
}

.words {
  justify-content: right;
  margin: 0px 0px 0px 10px;
  max-width: 90%;
  line-height: 1.6;
  border: 3px solid darkseagreen;
  border-radius: 5px;
  padding: 10px 10px 10px 10px;
}

.words2 {
  justify-content: right;

  margin: 0px 0px 0px 10px;
  padding: 10px 10px 10px 10px;
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
  padding: 0px 10px 0px 10px;
  margin: 0px 0px 0px 10px;
}

/* .afterafterwords {
  border: 3px solid darkseagreen;
  border-radius: 5px;
  padding: 10px 10px 10px 10px;
  margin: 0px 0px 0px 10px;
} */

.about-me {
  display: flex;
  flex-direction: row;
  
  list-style-type: none;
  align-content: space-between;
  padding: 0 0 0 0;
}
</style>