<script setup>
const currentDate = new Date();

const year = currentDate.getFullYear();
const month = currentDate.getMonth() + 1; 
const day = currentDate.getDate();

const formattedDate = `${day < 10 ? '0' : ''}${day}-${month < 10 ? '0' : ''}${month}-${year}`;

</script>

<template>
    <header class="welcome-text">
        <h1>Welcome to Opportunity</h1>
        <div class="date">
            <h2>{{ formattedDate }}</h2>
        </div>
    </header>
</template>

<style scoped>
.welcome-text{
    width: 764px;
    margin-top: 69px;
    margin-left: 60px;
}

h1{
    font-family: "Inter", sans-serif;
    font-size: 62px;
    font-weight: 900;
    line-height: 75.03px;
    color: rgba(50, 61, 74, 1);
}

.date{
    width: 370px;
    height: 75px;
    top: 165px;
    left: 60px;
    

}

h2 {
    font-family: "Inter", sans-serif;
    font-size: 61px;
    font-weight: 500;
    line-height: 75.03px;
    color: rgba(154, 167, 177, 1);  

}
</style>