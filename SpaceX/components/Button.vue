<template>
    <button class="Button">
        <slot>{{buttonText}}</slot>
    </button>
</template>

<script>
    export default{
        props: {
            buttonText: {
                type: String,
                default: () => "Label",

            },
        },
    };
</script>


<style lang="scss">
    @import "~assets/scss/variables";

    button{
    width: 100%;
    height: 3em;
    border-radius: 0.2em;
    border: 1px solid $white;
    background: none;
    color: $white;
    display: inline-block;

    &:hover{
        background: $white;
        color: $black;
        cursor: pointer;
    }
}

</style>