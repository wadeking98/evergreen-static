<template>
  <v-container>
    <v-card class="mt-2" elevation="0">
      <v-row>
        <v-col cols="12" lg="6" sm="12">
          <v-card-title>About the artist</v-card-title>
          <div class="text-left">
            <v-divider></v-divider>
            <v-card-text>
              Rose is an artist through and through. They have done it all from
              welding sculptures, pottery, carving, wood burning, painting,
              drawing, cooking, singing… everything! Since they were 10, they
              get up at 5AM just to paint, draw and create. They are a
              horticulturist and have a deep love of our natural flora and
              fauna. Drawing inspiration from the natural world, and the music
              they listen to, it makes their fingers dance to create beautiful
              things they hope to brighten the world with. Their current passion
              is high detail portraits, figure art, and botanical prints.
              They’ve competed in multiple art battles and enjoy bringing art to
              their community. Volunteering regularly at the Art Gallery of
              Greater Victoria, they love to help facilitate and bring art to
              young families and persons. <br /><br />
              There is no greater joy than to see the creativity of the mind
              bloom and blossom. They hope their art inspires people to focus on
              the important things in life: a home cooked meal, a beautiful
              garden, a loving family, and to care for the natural world in any
              way we can. May your day be filled with beauty, blossoms and
              sunshine! Rose 🌸
            </v-card-text>
          </div>
        </v-col>

        <v-col
        cols="12"
        lg="6">
            <div v-if="$vuetify.breakpoint.mdAndDown">
                <v-divider></v-divider>
            </div>
            <div class="image-container">
                <v-img v-for="image in json" :key="image" :src="require(`@/assets/images/Home/${image}`)" class="ma-2 mt-5 image-layout" max-width="30%"/>
            </div>
        </v-col>

        <v-col cols="12" sm="12">
          <v-card-title> Contact Information </v-card-title>
          <v-divider></v-divider>
          <v-card-text>
            <v-list>
              <v-list-item
                ><span
                  >Telephone:
                  <a class="contact-link" href="tel:778-677-7706"
                    >778-677-7706</a
                  ></span
                ></v-list-item
              >
              <v-list-item
                ><span
                  >Email:
                  <a class="contact-link" href="mailto:rose@heronweb.ca"
                    >rose@heronweb.ca</a
                  ></span
                ></v-list-item
              >
              <v-list-item
                ><span
                  >Insatgram:
                  <a
                    class="contact-link"
                    href="https://www.instagram.com/evergreens.art/"
                    >evergreens.art</a
                  ></span
                ></v-list-item
              >
            </v-list>
          </v-card-text>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>
<script>
import json from '@/assets/HomeWorks.json'
export default {
    name: 'index',
    data(){
        return{
            json:json
        }
    }
}
</script>
<style>
.image-container{
    display: flex;
    flex-wrap: wrap;
}
.image-layout{
    display: inline-flex;
    align-items: left;
}
</style>