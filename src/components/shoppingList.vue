<template>
  <v-carousel>
    <v-carousel-item
      v-for="(value,i) in values"
      :key="i"
    :src="fetchImage(value.name)"
    >
    <v-sheet
        color="rgba(0,0,0,0)"
        height="100%"
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div class="text-h2">
            {{ value.name }} 
          </div>
          
            <Chips
            :suppliers="value.suppliers"
            >
            </Chips>
        </v-row>
        
        
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</template>

<script>
import Chips from "./Chips.vue"

  export default {
    data () {
      return {
        
      }
    },
    methods:{
        fetchImage(itemName){
            //fetch image
            //return link
        }
    },
      props:{
          values:{
              type:Array
          }
        
  },
  components:{
      Chips,
    }
  }
</script>