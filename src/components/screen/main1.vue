<script setup>
import { defineProps } from 'vue'

defineProps({
    time: {
        type: String,
        required: true
    },
    date: {
        type: String,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    description: {
        type: String,
        required: true
    }
})

</script>

<template>
        <div class="blue">
            <div>
            <p class="orange">{{ time }} Uhr, &nbsp;{{ date }}</p>
            <p class="bage">{{ title }}</p>
            <p class="normal">{{ description }}</p>
            </div>
        </div>
</template>

<style scoped>
.blue{
    align-items: center;
    width:auto;
    margin: 60px;
    background-color: rgba(15,5,160,1);
}

.orange{
    font-family: "Inter", bolder;
    font-size: 28px;
    font-weight: 900;
    line-height: 36px;
    color: rgb(193, 115, 14);
}
.bage{
    font-family: "Inter", bolder;
    font-size: 28px;
    font-weight: 900;
    line-height: 36px;
    color: rgb(241, 163, 62);
}
.normal{
    font-family: "Inter", sans-serif;
    font-size: 28px;
    line-height: 36px;
    color: rgb(241, 163, 62);
}
.blue{
    padding: 50px;
}
</style>