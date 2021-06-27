<template>
    <div class="header">
        <h1 class="header__title">{{ title }}</h1>
        <p class="header__text">{{ text }}</p>
        <p class="header__text">Welcome! {{ username }}!</p>
        <label for="condition">How are you?</label>
        <input id="condition" type="text" :value="value" @input="$emit('input',$event.target.value)">
    </div>
</template>

<script>
export default {
    props: {
        username: String,
        value: String
    },
    data(){
        return {
            title: "Header",
            text: "Hello Vue.js!"
        }
    }
}
</script>

<style scoped lang="scss">
.header {
    border: 1px solid blue;
    padding: 15px;

    &__title {
        color: blue;
    }

    &__text {
        color:blue;
    }
}
</style>