<template>
    <header>
        <nav>
            <ul>
                <li><NuxtLink to="/" > Home </NuxtLink></li>
                <li><NuxtLink to="/launches" > Launches </NuxtLink></li>
                <li><NuxtLink to="/rockets" > Rockets </NuxtLink></li>
            </ul>
            <div class="hamburger">
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
            </div>	
        </nav>
    </header>

</template>


<style lang='scss'>
    @import "~assets/scss/variables";

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

    @media (min-width: 570px){
        header {
            margin: 2em 5em;
        }
    }

    @media (min-width: 992px){
        header {
            margin: 2em 5em;
        }
    }
</style>