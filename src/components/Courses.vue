<template>
    <div id="courses-container" :class="tab">
        <h1 class="title">Courses</h1>
        <table id="courses">
            <thead>
            <tr>
                <th>#</th>
                <th>Course Title</th>
                <th>Semester</th>
                <th>Grade</th>
            </tr>
            </thead>
            <tbody>
            <template v-for="(course, index) in courses">
                <tr :key="index">
                    <td>{{index}}</td>
                    <td>{{course.title}}</td>
                    <td>{{course.semester}}</td>
                    <td>{{course.grade}}</td>
                </tr>
            </template>
            </tbody>
        </table>
        <br>
        <br>
        <AddCourse :courses="courses"></AddCourse>
    </div>
</template>

<script>
    import AddCourse from "./AddCourse";
    export default {
        name: "Courses",
        components: {AddCourse},
        props: {
            courses: Array,
            tab: String,
        }
    }
</script>

<style scoped>

</style>