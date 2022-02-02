<template>
    <article class="rocketCard">
        <h2>{{ rocket.name }}</h2>
        <span class="active" v-if="!active">
            Status: Active
        </span>

        <span class="inactive" v-if="active">
            Status: Inactive
        </span>
        
        <img 
            :src="rocket.flickr_images[1]" 
            :alt="rocket.id"
        />

        <h3>Description</h3>
        <p class="description">
          {{ rocket.description }}
        </p>

        <div class="informationButtons">
            <ToggleButton
                labelText="Overview"
                v-model="firstOption"
            />
            <ToggleButton
                labelText="Engines"
                v-model="secOption"
            />
            <ToggleButton
                labelText="1st Stage"
                v-model="thirdOption"
            />
            <ToggleButton
                labelText="2nd Stage"
                v-model="fourthOption"
            />
        </div>

        <article v-if="firstOption">
            <h2>Overview</h2>
            <h3>Height</h3>
            <p>{{ rocket.height.meters }}m</p>

            <h3>Diameter</h3>
            <p>{{ rocket.diameter.meters }}m</p>

            <h3>Mass</h3>
            <p>{{ rocket.mass.kg }}kg</p>
        </article>

        <article v-if="secOption">
            <h2>Engines</h2>
            <h3>Type</h3>
            <p>{{rocket.engines.type}}</p>

            <h3>Version</h3>
            <p>{{rocket.engines.version}}</p>

            <h3>Layout</h3>
            <p>{{rocket.engines.layout}}</p>

            <h3>Proppellant 1</h3>
            <p>{{rocket.engines.propellant_1}}</p>

            <h3>Proppellant 2</h3>
            <p>{{rocket.engines.propellant_2}}</p>
       
            <h3>Thrust to weight 2</h3>
            <p>{{rocket.engines.thrust_to_weight}}</p>
        </article>

        <article v-if="thirdOption">
            <h2>1st Stage</h2>
            <h3>Engines</h3>
            <p>{{ rocket.first_stage.engines }}</p>

            <h3>Thrust at sea level</h3>
            <p>{{ rocket.first_stage.thrust_sea_level.kN }}kN</p>

            <h3>Thrust vacuum</h3>
            <p>{{ rocket.first_stage.thrust_vacuum.kN }}</p>

            <h3>Fuel capacity</h3>
            <p>{{ rocket.first_stage.fuel_amount_tons }}</p>

            <h3>Burn time</h3>
            <p>{{ rocket.first_stage.burn_time_sec }}sec</p>
        </article>

        <article v-if="fourthOption">
            <h2>2nd Stage</h2>
            <h3>Fuel capacity</h3>
            <p>{{ rocket.second_stage.fuel_amount_tons }}</p>

            <h3>Engines</h3>
            <p>{{ rocket.second_stage.engines }}</p>

            <h3>Engine burn time</h3>
            <p>{{ rocket.second_stage.burn_time_sec }}sec</p>

            <h3>Thrust</h3>
            <p>{{ rocket.second_stage.thrust.kN }}kN</p>
        </article>

    </article>
</template>

<script>
    export default {
        props: {
            rocket: {
                type: Object,
                default: () => {},
            },
            active: {
                type: String,
            }
        },

        data() {
            return {
                firstOption: false,
                secOption: false,
                thirdOption: false,
                fourthOption: false,
            };
        },
    };
</script>

<style lang="scss">
    @import "~assets/scss/variables";

    .rocketCard {
        img {
            height: 18em;
            width: auto;
        }

        .description{
            min-height: 8em;
        }

        article {
            padding: 1em;
            float: left;
            width: 12em;
            border: none;
            box-shadow: none;
        }

        .informationButtons {
            display: flex;
            flex-direction: row;

            label{
                flex-grow: 1;
            }
        }
    }
</style>
