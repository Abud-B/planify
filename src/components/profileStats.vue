<template>
  <v-sparkline
    :value="values"
    :color="colour"
    smooth="10"
    :fill="false"
    auto-draw
  ></v-sparkline>
</template>

<script>
    export default {
        data() {
            return {
                
            }
        },
        props:{
          colour:{
            type:String
          },
          values:{
              type:Array
          }

        }
    }
</script>

<style scoped>

</style>