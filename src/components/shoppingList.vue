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
           fetch(`https://api.unsplash.com/search/photos/?client_id=8Hw2GK9VED-X2W8Nb8DMcQ6RTCSC4T9onpEkG0x_G2U&query=${itemName}&content_filter=high`)
            .then(data => data.json())
            .then(data => {
              let numResults = data.results.length
              let randNum = Math.floor(Math.random() * numResults)
              console.log( data.results[randNum].urls.small)
            })
          
},
      props:{
          values:{
              type:Array
          }
        
  },
  components:{
      Chips
    }
  }}
</script>