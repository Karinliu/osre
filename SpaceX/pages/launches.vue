<template>
    <div class="container">
        <Header/>
        <section>
            <PageTitle
                titleText="Launches"
            />
        </section>
        <section>
            <LaunchCard 
            v-for="launch in launchSuccess.slice().reverse()" 
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
            launchSuccess: [],
            launchUnSuccess: [],
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
                if(launch.success == true){
                    this.launchSuccess.push(launch)
                }else{
                     this.launchUnSuccess.push(launch)
                }
            })
        }
    }
}
</script>
