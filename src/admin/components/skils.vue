<template lang="pug">
  #about
    h2.skils__title Страница «Обо мне»
    skills-row(
      v-for = "type in types"
      :key = "type.id"
      :type = "type"
      :skils = "skils"
      )

    

</template>

<script>
var data = [
  {id: 1, title: "Html", percent: 20, category: 0},
  {id: 2, title: "PHP", percent: 20, category: 1},
  {id: 3, title: "CSS", percent: 20, category: 0},
  {id: 4, title: "Node.js", percent: 20, category: 1},
  {id: 5, title: "Mongo", percent: 20, category: 1},
  {id: 6, title: "Git", percent: 20, category: 2},
  {id: 7, title: "Gulp", percent: 20, category: 1},
  {id: 8, title: "Javascript", percent: 20, category: 0},
  
];

import skillsRow from './skillsRow'

export default {
   components: {
    skillsRow
  },

  data(){
    return {
      types: [
        {id : 0, name: 'frontend'},
        {id : 1, name: 'backend'},
        {id : 2, name: 'worlflow'},
      ],
      skils: data
    }
  }
};




</script>

<style lang="scss" scoped>
  .skils__title {
    font-size: 21px;
    font-weight: 500;
    margin-bottom: 40px;
  }
</style>