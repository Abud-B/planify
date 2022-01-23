<template>
<v-container>
  <v-row>
    <v-col
    v-for="user in users"
    :key="user.name"
    cols="4"
    >

  
  <profileBox
  :name="user.name"
  :colour="user.colour"
  :quote="user.quote"
  :likes="user.likes"
  :shares="user.shares"
  :avatar="user.avatar"
  >
  </profileBox>

     <v-btn 
      @click="user.likes+=1"
      class="mx-2 mt-2"
      fab
      dark
      small
      color="pink"
    >
      <v-icon dark>
        mdi-heart
      </v-icon>
    </v-btn>

    <v-btn
      @click="user.shares+=1"
      class="mx-2 mt-2"
      fab
      dark
      small
      color="blue"
    >
      <v-icon dark>
        mdi-share-variant
      </v-icon>
    </v-btn>

  </v-col>
  

 <v-col
    v-for="user in users"
    :key="user.name"
    cols="4"
    >
  <profileStats
    :values="user.values"
    :colour="user.colour"
    >
  </profileStats>
</v-col>
<v-col>
    <shoppingList
    :values="shopping"
  >
    <template v-slot:default="data">
      <v-btn block color="primary" dark>{{data.name}}</v-btn>
    </template>
    </shoppingList>
  </v-col>


  </v-row>
</v-container>
</template>

<script>
import profileBox from "../components/profileBox.vue"
import profileStats from "../components/profileStats.vue"
import shoppingList from "../components/shoppingList.vue"
  export default {
    data: () => ({
      users:[
        {
          name:"Abud",
          quote:"ABC",
          colour:"red",
          likes:156,
          shares:40,
          avatar:"https://waste4change.com/blog/wp-content/uploads/niko-photos-tGTVxeOr_Rs-unsplash-1024x683.jpg",
          values:Array.from({length: 10}, () => Math.floor(Math.random() * 10))
        },
         {
          name:"Shakeeb",
          quote:"DEF",
          colour:"purple",
          likes:156,
          shares:40,
          avatar:"https://www.collinsdictionary.com/images/full/river_377603497_1000.jpg",
          values:Array.from({length: 10}, () => Math.floor(Math.random() * 10))


        }, 
        {
          name:"Hamada",
          quote:"GHI",
          colour:"green",
          likes:156,
          shares:40,
          avatar:"https://cdn.mos.cms.futurecdn.net/ntFmJUZ8tw3ULD3tkBaAtf.jpg",
          values:Array.from({length: 10}, () => Math.floor(Math.random() * 10))
        },
      ],
      shopping:[
        {
          name:"Milk",
          price:1.0,
          colour:"white",
          purchases:2,
          suppliers:["cravendale","tesco","asda","sainsburys"]
        },
        {
          name:"Bread",
          price:0.7,
          colour:"purple",
          purchases:1,
          suppliers:["kingsmill","hovis","tesco","asda","sainsburys"]
        },
        {
          name:"Crisps",
          price:1.75,
          colour:"red",
          purchases:2,
          suppliers:["walkers","mccoys","tesco","asda","sainsburys"]
        },
        {
          name:"cheese",
          price:5.0,
          colour:"blue",
          purchases:3,
          suppliers:["tesco","asda","sainsburys"]
        },
      ]

    }),
    components:{
      profileBox,
      profileStats,
      shoppingList,
    }
  }
</script>
