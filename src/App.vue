<template>
  <div>
    <div class="title-holder">
      <!-- <img class="me" src="./images/ruthface.png" alt="ruth's face" width="100px" /> -->
      <h2 id="title">Ruth Foulis</h2>
      <h4 id="subtitle">Software Developer</h4>
      <nav>
        <ul class="nav-list">
          <li></li>
          <li class="list-item" v-on:click="clickAbout">About</li>
          <a
            href="https://www.linkedin.com/in/ruth-foulis-7263031aa/"
            target="_blank"
            class="list-item"
            ><li>LinkedIn</li></a
          >
          <a
            href="https://github.com/ruthierutho"
            target="_blank"
            class="list-item"
          >
            <li>GitHub</li></a
          >
          <a
            href="https://twitter.com/ruthlilfoulis"
            target="_blank"
            class="list-item"
          >
            <li>Twitter</li></a
          >

          <a
            href="mailto:ruthlilfoulis@gmail.com"
            target="_blank"
            class="list-item"
            ><li>Email</li></a
          >
        </ul>
      </nav>
    </div>
    <about-me
      v-if="selectedAbout"
      :about="selectedAbout"
      class="about"
    ></about-me>
    <my-projects :projects="projects"></my-projects>

    <modal
      name="project-modal"
      width="700"
      height="auto"
      :adaptive="true"
      :reset="true"
      :scrollable="true"
    >
      <div class="pop-content">
        <button id="close" @click="hide()">x</button>
        <project-detail
          v-if="selectedProject"
          :project="selectedProject"
        ></project-detail>
      </div>
    </modal>
    <footer>Made with Vue. Ruth Foulis 2021©</footer>
  </div>
</template>

<script>
import { eventBus } from "./main.js";

import myProjects from "./components/myProjects.vue";
import projectDetail from "./components/projectDetail.vue";
import aboutMe from "./components/aboutMe.vue";

export default {
  name: "app",
  data() {
    return {
      projects: [
        {
          name: "Disneyland Bucket List: Solo Python Project",
          specs:"Created using Python, Flask, PostgreSQL, HTML, CSS, Unittest.",
          details:
            "This app was created solo in about six days. It is full-stack web app allowing users to add and edit Disneyland Paris attractions to their ‘still to see’ list and update entries once an attraction has been visited. This app was really fun to make and really grew my confidence with Python, handling routes and coding in general. The colour scheme may not be for everyone but I like it!!",
          github:
            "https://github.com/ruthierutho/disneyland_bucketlist_python_project",
          deploy: "https://dsneyland-python-app.herokuapp.com/attractions",
        },
        {
          name: "Fruits of the World: Group Javascript/Vue Project",
          specs: "Created using Javascript, Vue.js, Express.js, Node.js, MongoDB, Leaflet, Highcharts, Modal.js, Web APIs.",
          details:
            "This app was created in a group of three, over six and a half days. It is full-stack educational web app detailing nutritional and origin information on a selection of different fruits. Pitched at 9-12 year olds for use in the classroom to aid learning on food nutrition, we wanted to create a fun and friendly app and I think we achieved that! Each team member worked on a different feature- pop ups, maps, charts- and it all came together really nicely. I had a lot of fun learning about modals and really enjoyed refactoring the project more recently to bring a bigger interactive map to the main page.",
          github: "https://github.com/ruthierutho/fruit_app_javascript_project",
          deploy: "https://ruthierutho.github.io/fruit_app_javascript_refactor/"
        },
        {
          name: "RoundIn Ordering: Group Java/React Project",
          specs: "Created using a Spring backend with an H2 database, with a React front end for venues and for customers.",
          details:
            "This app was created in a group of four, over seven days. It is a full-stack web app allowing customers and venues to handle and organise remote pre-bookings for food and drink orders. There are separate venue and customer frontends. This project was a big challenge! We all felt very new to React when we started but took on the steep learning curve and ended up with a well functioning and feasible app.",
          github: "https://github.com/ruthierutho/roundIn-ordering-app",
          photo: "./images/beer.png",
        },
        {
          name: "Music Box: Post-CodeClan Solo React App",
          specs: "Created using React.",
          details: "This is a fun app for kids! Users can click the musical instrument buttons to hear them play, or hit the 'Play' button to display prompts to find specific instruments. Further extensions for this project would be to add a 'hard mode' for the questions to challenge the user further and to add a voice command for the questions too.",
          github: "https://github.com/ruthierutho/music-box-react",
          deploy: "https://ruthierutho.github.io/music-box-react/"
        
        }
      ],
      selectedProject: null,
      selectedAbout: null,
    };
  },

  mounted() {
    eventBus.$on("project-selected", (project) => {
      this.selectedProject = project;
      this.show();
    }),
      eventBus.$on("about-selected", (about) => {
        this.selectedAbout = null;
      });
  },

  methods: {
    clickAbout(about) {
      this.selectedAbout = about;
    },

    show() {
      this.$modal.show("project-modal");
    },
    hide() {
      this.$modal.hide("project-modal");
    },
  },

  components: {
    "my-projects": myProjects,
    "project-detail": projectDetail,
    "about-me": aboutMe,
  },
};
</script>

<style>
body {
  background-color: rgb(253, 238, 230);
  padding: 0 0 0 0;
  margin-top: 0;
 align-content: center;
  justify-content: center;
  justify-items: center;
}

.title-holder {
  border: 1px;
  background-color: rgb(253, 238, 230);
  padding: 20px;

  text-align: center;
}
#title {
  font-family: "Montserrat", sans-serif;
  font-size: 60pt;
  background-color: rgb(253, 238, 230);
  color: turquoise;
  padding: 20px;
  padding-bottom: 0;
  padding-top: 0;
  margin: 10px;
  margin-top: 0px;
  text-align: center;
  align-content: center;
  justify-content: center;
}

#subtitle {
  font-family: "Montserrat", sans-serif;
  font-size: 20pt;
  padding-top: 0;
  color: seagreen;
  justify-content: center;
}

.nav-list {
  list-style-type: none;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  /* display: grid;
  grid-template-areas: 
    'nothing item item item item nothing';
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr; */
  padding: 10px 10px 10px 20px;
  align-content: center;
  align-items: center;
  justify-content: center;
}

.about {

  border: 1px;
  background-color: darkgreen;
  padding: 1%;
  margin: 0% 10% 0% 10%;
  align-items: center;
  align-content: center;
  justify-content: center;
  border-radius: 10px;
  font-family: "Montserrat", sans-serif;
  color: turquoise;
  cursor: pointer;

}
.list-item {
  font-family: "Montserrat", sans-serif;
  font-size: 14pt;
  background-color: seagreen;
  color: turquoise;
  border-radius: 5px;
  padding: 10px;
  margin: 10px;
  text-align: center;
  text-decoration: none;
}

.list-item:hover {
  background-color: darkseagreen;
  color: seagreen;
  cursor: pointer;
}

.pop-content {
  background-color: seagreen;
  font-family: "Montserrat", sans-serif;
  padding: 20px 20px 20px 20px;
  color: darkseagreen;
  overflow-y: auto;
  height: 100%;
  justify-content: center;

}

#close {
  font-family: "Montserrat", sans-serif;
  font-size: 14pt;
  background-color: seagreen;
  color: turquoise;
  border-radius: 5px;
  text-align: center;
  align-content: right;
}

/* .me {
  background-color: darkseagreen;
  border-radius: 5px;
  align-self: left;
} */

footer {
  font-family: "Montserrat", sans-serif;
  color: turquoise;
  width: 100%;
  border: 1px;
  background-color: rgb(253, 238, 230);
  padding: 20px;

  text-align: center;
}
</style>
