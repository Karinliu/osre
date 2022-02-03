<template>
    <div class="container">
        <Header/>
        <section>
            <PageTitle
                titleText="404"
            />
        </section>
        <section>
            <h2>Oops! We lost this page in space</h2>
            <img src="~@/assets/images/mochitherocketman.png" alt="Mochi in a racket">
        </section>

        <section>
            <NuxtLink class="home-btn" to="/" > Go back to home </NuxtLink>
        </section>

    </div>
</template>

<style lang="scss">
    @import "~assets/scss/variables";
    @import "~assets/scss/animation";

    h2{
        color: $white;
    }
    
    img{
        height: 20em;
        animation: MoveUpDown 1s linear infinite;
        position: absolute;
        right: 0;
        left: 0;
        margin: 0 auto;
    }

    .home-btn{
        color: $white;
        text-decoration: none;
        border: 1px solid $white;
        padding: 1em;
        width: fit-content;

        &:hover{
            color: $black;
            background: $white;
            opacity: 1;
        }
    }

    @media (max-width: 576px){
        img {
            max-width: 540px;
            margin: auto;
        }
    }


</style>