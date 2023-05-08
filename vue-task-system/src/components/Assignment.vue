<template>
    <div>
        <label>
            {{ title }}
            <input type="checkbox" name="" id="">
        </label>
    </div>
</template>


<script>
export default {
    name: "assignment",
    props:{
        assignments: Array,
        title: String,
        // complete:{
        //     type:Boolean
        // }
    }
}
</script>