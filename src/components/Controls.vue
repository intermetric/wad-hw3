<template>
    <div class="controls">
        <button id="profile-button" :class="{'pill active' : tabs.profile==='tab active', 'pill' : tabs.profile==='tab'}" @click="selectTab('profile')">Profile</button>
        <button id="courses-button" :class="{'pill active' : tabs.courses==='tab active', 'pill' : tabs.courses==='tab'}" @click="selectTab('courses')">Courses</button>
    </div>
</template>

<script>
    export default {
        name: "Controls",
        props: {
            selectTab: Function,
            tabs: Object
        }
    }
</script>

<style scoped>

</style>