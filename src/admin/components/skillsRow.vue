<template lang="pug">
    .skills-row
        h2.title {{type.name}}
        table.table
            skills-Item(
                v-for = "skill in skils"
                v-if = "type.id === skill.category"
                :key = "skill.id"
                :skill = "skill"
            )
            skills-Item(
                :editMode = "true"
            )
        hr
</template>

<script>
import skillsItem from './skillsItem'
export default {
    components: {
        skillsItem
    },
    props: {
        type: {
            type: Object,
            default: () => {}
        },
        skils: {
            type: Array,
            default: () => []
        }
    }
}
</script>
