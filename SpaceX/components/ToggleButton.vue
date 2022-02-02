<template>
    <label>
        <input 
          type="checkbox" 
          v-model="checked" 
          @change="onChange">
          <span>{{labelText}}</span>
      </label>
</template>

<script>
    export default{
        props: {
            labelText: {
                type: String,
                default: "",
            },

        },
        prop: ['value'],
            data () {
                return {
                checkedProxy: false,
                }
            },
            computed: {
                checked: {
                get () {
                    return this.value
                },
                set (val) {
                    this.checkedProxy = val
                }
                }
            },
            methods: {
                onChange: function(e) {
                    this.$emit('input', this.checkedProxy)
                }
            }
        
    }
</script>

<style lang="scss">
    @import "~assets/scss/variables";

    label{
        border: 1px solid $white;
        display: block;
        margin-top: 1em;
        text-align: center;
        padding: 0.5em;
        color: $white;

        &:hover{
            cursor: pointer;
            background-color: $white;
            color: $black;
        }

        input[type="checkbox"]{
            display: none;
        }

        input[type=checkbox]:checked{
            + span{
                font-style: italic;
                font-weight: 600;
            }
        }
    }
</style>