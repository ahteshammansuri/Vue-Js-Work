
<script>
import AssignmentList from "./AssignmentList.vue";

export default {

    data() {
        return {
            assignments: [
                { id: 1, name: "First Project", completed: false },
                { id: 2, name: "Second Project", completed: false },
                { id: 3, name: "Third Project", completed: false }
            ]
        };
    },

    computed: {
        inCompletedTask() {
            return this.assignments.filter(a => !a.completed);
        },
        completedTask() {
            return this.assignments.filter(a => a.completed);
        }
    },

    components: {
        AssignmentList,
    },
}
</script>

<template>
    <AssignmentList :assignments="inCompletedTask" title="In Progress"></AssignmentList>
    <AssignmentList :assignments="completedTask" title="Completed"></AssignmentList>
</template>

<style></style>