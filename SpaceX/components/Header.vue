<template>
    <header>
        <nav>
            <ul>
                <li><NuxtLink to="/" > Home </NuxtLink></li>
                <li><NuxtLink to="/launches" > Launches </NuxtLink></li>
                <li><NuxtLink to="/rockets" > Rockets </NuxtLink></li>
            </ul>
        </nav>
    </header>
</template>


<style lang='scss'>
    @import "~assets/scss/variables";

    header{
        padding: 0.5em 5em;

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
</style>