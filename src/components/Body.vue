<template>
    <div class="body">
        <h2 class="body__title">{{ title }}</h2>
        <p class="body__text">{{ text }}</p>
        <p><button @click="increment">+1</button> {{ count }} </p>
    </div>
</template>

<script>
export default {
    data(){
        return {
            title: "Body",
            text: "Have a good day!",
            count: 0
        }
    },
    methods: {
        increment(){
            this.count += 1;
            this.$emit("add",this.count);
        }
    }
}
</script>

<style scoped lang="scss">
.body {
    border: 1px solid red;
    margin: 5px 0;
    padding: 15px;

    &__title {
        color: red;
    }
    &__text {
        color: red;
    }
}
</style>