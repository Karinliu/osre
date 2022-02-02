<template>
    <a 
        target="_blank"
        v-bind:class="''"
        v-bind:href="''"
    >
        {{linkText}}
    </a>

</template>

<script>
    export default{
        props: {
            linkText: {
                type: String,
                default: () => "",

            },
        },
    };
</script>


<style lang="scss">
    @import "~assets/scss/variables";

</style>