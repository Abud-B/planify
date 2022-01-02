<template>
<div>
  Hello
  <profileBox>
  </profileBox>
  
</div>
</template>

<script>
import profileBox from "../components/profileBox.vue"
  export default {
    data: () => ({
      users:[
        {
          name:"Abud",
          quote:"ABC",
          colour:"red",
        },
         {
          name:"Shakeeb",
          quote:"DEF",
          colour:"purple",
        }, 
        {
          name:"Hamada",
          quote:"GHI",
          colour:"green",
        },
      ]

    }),
    components:{
      profileBox
    }
  }
</script>
