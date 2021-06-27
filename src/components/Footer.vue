<template>
    <div class="footer">
        <h1 class="footer__title">{{ title }}</h1>
        <p class="footer__text">{{ text }}</p>
        <p class="footer__text">{{ userage }} years old</p>
    </div>
</template>

<script>
export default {
    data(){
        return {
            title: "Footer",
            text: "Hello Vue.js!"
        }
    },
    props: {
        userage: String
    }
}
</script>

<style scoped lang="scss">
.footer {
    border: 1px solid Green;
    padding: 15px;

    &__title {
        color: Green;
    }

    &__text {
        color:Green;
    }
}
</style>