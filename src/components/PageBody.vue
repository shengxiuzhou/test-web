<template>
     <div class="body-container">
        <Gallary></Gallary>
        <Partner></Partner>
    </div>
</template>


<script setup>
    import Gallary from './Gallary.vue'
    import Partner from './Partner.vue'
</script>

<style scoped>
.body-container {
    width:80%;
    height:500px;
    margin: 0 auto;
}
</style>