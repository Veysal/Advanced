<template lang="pug">
    tr(v-if = "editMode === false")
        td {{skill.title}}
        td {{skill.percent}}
        td
            button(type = 'button') Удалить

    tr(v-else)
        td
            input(type = 'text' placeholder = "name")
        td
            input(type = 'text' placeholder = "percent")
        td
            button(type = "button" @click = "addNewSkill(newSkill)") Добавить
</template>

<script>
import { mapActions } from "vuex"
export default {
    props: {
        skill: {
            type: Object,
            default: () => {}
        },
        editMode: {
            type: Boolean,
            default: false
        }
    },

    data(){
        return {
            newSkill: {
                title: "",
                percents: "",
                category: 0
            }
        }
    },
    methods: {
        ...mapActions({
            addNewSkill: "skills/add"
        })
    }
}
</script>

