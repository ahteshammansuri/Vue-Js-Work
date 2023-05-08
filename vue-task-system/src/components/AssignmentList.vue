<template>
    <div v-if="assignments.length">
        <h3> {{ title }} </h3>
        <label v-for="item in assignments" :key="item.id">
            <br>
            {{ item.name }}
            <input type="checkbox" name="" id="" v-model="item.completed">
        </label>
    </div>
</template>

<script>
export default {
    name:"AssignmentList",
    props: {
        assignments: Array,
        title: String
    }
}
</script>
