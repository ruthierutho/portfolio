<template>
  <div class="pop" v-if="project">
    <b
      ><h2 class="project-title">{{ project.name }}</h2></b
    >
    <p class="detail-words">{{ project.details }}</p>
    <div class="detail-info">
      <h4>{{ project.specs }}</h4>
      <h4>Github: <a :href="project.github" target="_blank">Click here!</a></h4>

      <h4 v-if="project.deploy != null">
        Deployed: <a :href="project.deploy" target="_blank">Click here!</a>
      </h4>
    </div>
    <div
      class="photo-container"
      v-if="
        project.name === 'Fruits of the World: Group Javascript/Vue Project'
      "
    >
      <img
        class="image"
        src="../images/fruits1.png"
        alt="fruits project screen grab 1"
        width="95%"
      />
      <img
        class="image"
        src="../images/fruits2.png"
        alt="fruits project screen grab 2"
        width="95%"
      />
      <img
        class="image"
        src="../images/fruits3.png"
        alt="fruits project screen grab 3"
        width="95%"
      />
    </div>
    <div
      class="photo-container"
      v-else-if="project.name === 'Disneyland Bucket List: Solo Python Project'"
    >
      <img
        class="image"
        src="../images/dland1.png"
        alt="disneyland"
        width="95%"
      />
      <img
        class="image"
        src="../images/dland2.png"
        alt="disneyland"
        width="95%"
      />
      <img
        class="image"
        src="../images/dland3.png"
        alt="disneyland"
        width="95%"
      />
    </div>
    <div
      class="photo-container"
      v-else-if="
        project.name === 'RoundIn Ordering: Group Java/React Project'
      "
    >
      <img
        class="image"
        src="../images/Roundin.png"
        alt="disneyland"
        width="95%x"
      />
    </div>

    <div
      class="photo-container"
      v-else-if="project.name === 'Music Box: Post-CodeClan Solo React App'"
    >
      <img
        class="image"
        src="../images/music-box1.png"
        alt="music box screen grab"
        width="95%"
      />
      <img
        class="image"
        src="../images/music-box2.png"
        alth="music box screen grab 2"
        width="95%"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "project-detail",
  props: ["project"],
};
</script>

<style>
.pop {
  background-color: seagreen;
}

.project-title {
  color: darkgreen;
}

.image {
  border: 4px solid darkgreen;
  justify-content: center;
}

.detail-words {
  background-color: darkseagreen;
  color: darkgreen;
  border-radius: 5px;
  padding: 10px;
}

.detail-info {
  border: 2px solid darkseagreen;
  border-radius: 5px;
  padding: 10px 10px 10px 10px;
  margin: 10px 0px 10px 0px;
}

.photo-container {
  border: 3px solid darkseagreen;
  border-radius: 5px;
  padding: 10px 10px 10px 10px;
  justify-content: center;
}
</style>