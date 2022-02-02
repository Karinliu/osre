<template>
    <h1>
        <slot>{{titleText}}</slot>
    </h1>
</template>

<script>
    export default{
        props: {
            titleText: {
                type: String,
                default: "",
            },

        },
    }
</script>

<style lang="scss">

    @import "~assets/scss/variables";

    h1{
        margin: 0;
        font-size: 2.5em;
        color: $white;
    }

</style>