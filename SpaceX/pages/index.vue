<template>
    <div class="container">
        <Header/>
        <section>
            <PageTitle
                titleText="Upcoming"
            />
        </section>
        <section>
            <LaunchCard 
            v-for="launch in launches.slice().reverse()" 
            :key="launch.id"
            :launch="launch" 
            />
        </section>

    </div>
</template>

<script>
import axios from 'axios'

export default{
    data(){
        return{
            launches: []
        }
    },
    async fetch() {
        await this.getLaunches()
    },
    methods: {
        async getLaunches(){
            const data = axios.get(
                'https://api.spacexdata.com/v4/launches'
            )
            const result = await data

            result.data.forEach((launch) => {
                if(launch.upcoming == true){
                    this.launches.push(launch)
                }else{

                }

            })
        }
    }
}
</script>
