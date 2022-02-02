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

    @media (min-width: 570px){
        header {
            margin: 2em 5em;
        }
    }

    @media (max-width: 768px) {
        button{
            display: block;
			width: 50px;
			height: 50px;
			background: none;
			border: none;
			position: absolute;
			z-index: 100;
			cursor: pointer;

            span{
				display: block;
				width: 20px;
				height: 2px;
				margin: auto;
				background: $white;
				position: absolute;
				top: 0;
				bottom: 0;
				left: 0;
				right: 0;
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
                        transform: rotate(-45deg);
                    }
                    .mid{
                        transform: translateX(-20px) rotate(360deg);
                        opacity: 0;
                    }
                    .bottom {
                        transform: rotate(45deg);
                    }
                }
        }


        nav{
            display: none;

            &.active{
                display: block;
            }
        }
    }

    @media (min-width: 992px){
        header {
            margin: 2em 5em;
        }
    }
</style>