<template>
  <v-grid>
    <v-row>
      <v-col >
        <v-card class="mx-auto mt-5" max-width="344">
          <v-img height="200px" :src="product.image"></v-img>
          <v-row justify="space-around">
          <v-card-title>
            {{ product.title }}
          </v-card-title>

          <v-card-subtitle>
            {{ product.subtitle }}
          </v-card-subtitle>
        </v-row>
          <v-card-actions>
            <v-btn @click="show = !show" style="background-color: rosybrown"> Explore </v-btn>

            <v-spacer></v-spacer>
            <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
          </v-card-actions>

          <v-expand-transition>
            <div v-show="show">
              <v-divider></v-divider>

              <v-card-text>
                {{ product.text }}
              </v-card-text>
            </div>
          </v-expand-transition>
        </v-card>
      </v-col>
    </v-row>
  </v-grid>
  </template>

<script>
export default {
  props :{
    product :{
      type: Object,
      required: true
    }
  },
  data () {
    return {
      show: false,
      
    };
  },
};
</script>