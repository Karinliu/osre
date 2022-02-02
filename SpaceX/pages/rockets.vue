<template>
    <div class="container">
        <Header/>
        <section>
            <PageTitle
                titleText="Rockets"
            />
        </section>
        <section>
            <ToggleButton
                labelText="View retired rockets" 
                v-model="inActive"
            />
        </section>

        <section>
            <RocketCard 
            v-for="rocket in rocketsActive" 
            :key="rocket.id"
            :rocket="rocket" 
            :active="active"
            />
        </section>

        <section v-if="inActive" >
            <RocketCard 
            v-for="rocket in rocketsInActive" 
            :key="rocket.id"
            :rocket="rocket"
            :active="inActive"
            />
        </section>
    </div>
</template>

<script>
import axios from 'axios'

export default{
    data(){
        return{
            rocketsActive: [],
            rocketsInActive: [],
            inActive: false,
        }
    },
    async fetch() {
        await this.getRockets()
    },
    methods: {
        async getRockets(){
            const data = axios.get(
                'https://api.spacexdata.com/v4/rockets'
            )
            const result = await data

            result.data.forEach((rocket) => {
                if(rocket.active == true){
                    this.rocketsActive.push(rocket)
                }else{
                     this.rocketsInActive.push(rocket)
                }
            })
        }
    }
}
</script>
