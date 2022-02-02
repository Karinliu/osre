<template>
    <article class="launchCard">
      <h2>{{launch.name}} </h2>

      <p class="status">
            <span class="success" v-if="success">
                Status: {{success}}
            </span>

            <span class="unsuccess" v-if="unsuccess">
                Status: {{unsuccess}}
            </span>
      </p>

      <img 
        v-if="launch.links.patch.small"
        :src="launch.links.patch.small" 
        :alt="launch.id">

        <DefaultImage v-else />

        <h3>Flight number</h3>
        <p>{{launch.flight_number}}</p>
        
        <h3 v-if="launch.details">Description</h3>
        <p v-if="launch.details">{{launch.details}} </p>

        <linkWebsite v-if="launch.links.wikipedia"
          v-bind:class="'wikipedia'"
          v-bind:href="`${launch.links.wikipedia}`"
          linkText= "Wikipedia"
        />

        <linkWebsite v-if="launch.links.webcast"
          v-bind:class="'youtube'"
          v-bind:href="`${launch.links.webcast}`"
          linkText= "Youtube"
        />

    </article>
</template>

<script>
    export default {
        props: {
            launch: {
                type: Object,
                default: () => {},
            },
            success: {
                type: String,
            },
            unsuccess: {
                type: String,
            }
        },
    };
    
</script>

<style lang="scss">
    @import "~assets/scss/variables";

    .launchCard{
        img{
            width: 6em;
        }

        .status{
          display: inline-block;
          margin: 0;
          margin-left: 1em;
          color: $black;

          span{
              padding: 0.5em;
              border-radius: 0.5em;
          }

          .success{
              background: $green;
              box-shadow: 0.2em 0.2em 1em 0em $green;
          }

          .unsuccess{
              background: red;
              box-shadow: 0.2em 0.2em 1em 0em red;
          }
        }

        a{
            background-size: contain;
            display: inline-block;
            background-repeat: no-repeat;
            width: 7em;
            padding-left: 1.5em;
            color: $white;
        }

        .wikipedia{
            background-image: url('~@/assets/images/wikipedia-logo.png');
        }

        .youtube{
            background-image: url('~@/assets/images/youtube-logo.png');
        }
    }

</style>
