<template>
<div>
<v-hover
        v-slot="{ hover }"
        open-delay="200"
         v-for="(supplier,i) in suppliers"
      :key="i"
      >
  <div class="text-center">
    <v-chip
      :class="hover ? 'elevation-10' : 'elevation-2'"
      class="ma-2"
    >
      {{supplier}}
    </v-chip>

  </div>
      </v-hover>
      </div>
  
</template>

<script>
  export default {
    data () {
      return {
        
      }
    },
      props:{
          suppliers:{
              type:Array
          }
        }
  }
</script>
