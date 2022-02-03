<template>
    <header>
        <button 
            v-on:click="navOpen=!navOpen" 
            v-bind:class="{active:navOpen}">
				<span class="top"></span>
				<span class="mid"></span>
				<span class="bottom"></span>
		</button>
        <transition name="translateX">
        <nav v-bind:class="{active:navOpen}">
            <ul>
                <li><NuxtLink to="/" > Home </NuxtLink></li>
                <li><NuxtLink to="/launches" > Launches </NuxtLink></li>
                <li><NuxtLink to="/rockets" > Rockets </NuxtLink></li>
            </ul>
        </nav>
        </transition>
    </header>

</template>

<script>

export default ({
    data(){
        return{
            navOpen: false,
        }
    },
})
</script>


<style lang='scss'>
    @import "~assets/scss/variables";

    button{
        display: none;
    }

    header{
        margin: 2em 2em;

        nav{
            ul{
                display: flex;
                align-items: center;
                justify-content: right;

                li{
                    text-transform: uppercase;
                    list-style: none;
                    margin-left: 3em;

                    a{
                        color: $white;
                        text-decoration: none;
                    }

                    a.nuxt-link-exact-active {
                        font-weight: bold;
                    }
                }
            }
        }
    }

    @media (max-width: 570px) {
         header {
            position: fixed;
            width: 100vw;
            margin: 0;
            height: 5em;
            top: 0;
            background: $black;
    
                button{
                    display: inline-block;
                    width: 2em;
                    height: 2em;
                    background: none;
                    border: none;
                    z-index: 100;
                    cursor: pointer;
                    margin: 2em;
                    position: relative;
                    z-index: 100;

                    span{
                        display: block;
                        width: 20px;
                        height: 2px;
                        margin: auto;
                        background: $white;
                        transition: all .4s ease;

                        &.top {
                            transform: translateY(-8px);
                        }

                        &.bottom {
                            transform: translateY(8px);
                        }
                    }
                    &.active{

                            .top {
                                transform: translateY(2px)  rotate(-45deg);
                                background: $black;
                            }
                            .mid{
                                transform: translateX(-20px) rotate(360deg);
                                opacity: 0;
                            }
                            .bottom {
                                transform: translateY(-1px) rotate(45deg);
                                background: $black;
                            }
                        }
                }


                nav{
                    background: $white;
                    position: fixed;
                    transition-duration: 0.5s;
                    left: -100%;
                    width: 15em;
                    top: 0;
                    height: 100vh;
                    

                    &.active{
                        transition-duration: 0.5s;
                        left: 0;
                        // display: block;
                    }
                    ul{
                        display: flex;
                        flex-direction: column;
                        margin: 5em 2em;
                        padding: 0;

                        li{
                            height: 3em;
                            width: 100%;
                            margin: 0;

                            a{
                                color: $black;
                            }
                        }
                    }
                }
        }
    }

    @media (min-width: 992px){
        header {
            margin: 2em 5em;
        }
    }
</style>