<script >

import axios from 'axios';

import ProjectCard from './components/ProjectCard.vue';

export default{
  name: "App",
  components: {
    ProjectCard,
  }

}

</script>

<template>
  <ProjectCard></ProjectCard>
</template>

<style lang="scss">
@use './style/main.scss';
</style>
