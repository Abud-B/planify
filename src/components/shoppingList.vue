<template>
  <v-carousel>
    <v-carousel-item
      v-for="(value,i) in values"
      :key="i"
    :src="value.image"
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
            <slot :name="value.name">
              {{ value.name }} 
            </slot>

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
    created(){
      for (let value of this.values){
        this.fetchImage(value.name)
         .then(data => data.json())
            .then(data => {
              let numResults = data.results.length
              let randNum = Math.floor(Math.random() * numResults)
              this.$set(value, 'image', data.results[randNum].urls.small)

            })
      }
      console.log(this.values)
    },
    methods:{
       fetchImage(itemName){
           return fetch(`https://api.unsplash.com/search/photos/?clientID&query=${itemName}&content_filter=high`)
           
          
      },
    },
    props:{
          values:{
              type:Array
          }
        
  },
  components:{
      Chips
    }
  }
</script>