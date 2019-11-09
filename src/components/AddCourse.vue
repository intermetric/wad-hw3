<template>
    <div>
        <button id="add-course-button" class="blue-button" @click="selected = !selected">+</button>
        <span v-if="selected">
            <input class="input" type="text" placeholder="Course title" v-model="title">
            <input class="input" type="number" min="1" max="8" placeholder="Semester" v-model="semester">
            <input class="input" type="number" min="0" max="100" placeholder="Grade" v-model="grade">
            <button class="green-button" id="save-course" @click="saveCourse()">Save</button>
            <button class="grey-button" id="cancel-course" @click="selected = false">Cancel</button>
        </span>
    </div>
</template>

<script>
    import Course from '../models/Course'

    export default {
        name: "AddCourse",
        data: () => {
            return {
                selected: false,
                title: "",
                semester: "",
                grade: ""
            }
        },
        methods: {
            saveCourse: function() {
                this.courses.push(new Course(this.title, this.semester, this.grade));
                this.selected = false;
                this.title = "";
                this.semester ="";
                this.grade = ""
            }
        },
        props: {
            courses: Array,
        }
    }
</script>

<style scoped>

</style>