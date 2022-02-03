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

    @media (max-width: 570px) {
        h1{
            z-index: 1;
            text-align: center;
            position: fixed;
            left: 0;
            right: 0;
            font-size: 2em;
            top: 0.6em;
            width: fit-content;
            margin: 0 auto;
        }

    }


</style>