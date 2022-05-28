<template>
  <div>
    <v-container>
      <v-card class="mt-2" elevation="0">
        <v-card-title>{{ title }}</v-card-title>
      </v-card>
      <v-card
        v-for="item in json"
        :key="item.title"
        elevation="0"
        class="mb-5"
        outlined
      >
        <v-card-title v-if="item.title" class="content">{{
          item.title
        }}</v-card-title>
        <div class="image-container">
          <v-card
            elevation="0"
            v-for="(image, i) in item.image"
            :key="i"
            width="100%"
          >
            <img
              :src="require(`@/assets/images/${imageFolder}/${image}`)"
              class="ma-2 image-layout"
            />
            <v-card-actions>
              <v-col v-if="download" align-self="end" class="text-right">
                <v-btn
                  :href="require(`@/assets/images/${imageFolder}/${image}`)"
                  download
                  icon
                >
                  <v-icon>mdi-download</v-icon>
                </v-btn>
              </v-col>
            </v-card-actions>
          </v-card>
        </div>
        <v-card-text class="text-left">
          {{ item.description }}
        </v-card-text>
        <v-card-text v-if="item.cost"> Cost: {{ item.cost }} </v-card-text>
      </v-card>
    </v-container>
  </div>
</template>
<script>
export default {
  name: "PageComponent",
  props: ["json", "title", "imageFolder", "download"],
};
</script>

<style>
.content {
  word-break: break-word;
}

.image-container {
  display: flex;
  flex-wrap: wrap;
}

.image-layout {
  display: block;
  align-items: left;
  max-height: 80vh;
  max-width: 90%;
}
</style>
