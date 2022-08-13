<template>
  <div>
    <input type="number" ref="number" id="number">
    <button @click="show_item">submit</button>
<div class="all" ref="all"  >
    <div ref="each" v-for="(item,index) in items" :key="index">
    <h2>{{item[`title`]}}</h2>
    <p>{{item[`price`]}}</p>
    <p>{{item[`description`]}}</p>
    <img :src="item[`image_url`]" :alt="`image${item[`descriptiom`]}`">
    </div>

</div>
<div class="price_sel" v-for="(item,index) in items" :key="index">
  <div v-if="item[`price`] <= number_value"> 
    <h2>{{item[`title`]}}</h2>
    <h2>{{item[`price`]}}</h2>
    <img :src="item[`image_url`]">
  </div>
</div>
    
  </div>
</template>

<script>
export default {
    methods: {
        show_item() {
         this.number_value = this.$refs[`number`][`value`];
        }
    },

  data() {
    return {
        number_value: undefined,
      items: [
        {
          title: `title_one`,
          price: 100,
          description: `description_one`,
          image_url: `https://images.unsplash.com/photo-1660388330411-26f4cf299a64?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw0fHx8ZW58MHx8fHw%3D&auto=format&fit=crop&w=500&q=60`,
        },
        {
             title: `title_two`,
          price: 200,
          description: `description_two`,
          image_url: `https://images.unsplash.com/photo-1660395354694-6b331dc75969?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw3fHx8ZW58MHx8fHw%3D&auto=format&fit=crop&w=500&q=60`
        },
        {
             title: `title_three`,
          price: 300,
          description: `description_three`,
          image_url: `https://images.unsplash.com/photo-1660358817617-620fbe0887c3?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyMHx8fGVufDB8fHx8&auto=format&fit=crop&w=500&q=60`
        },
      ],
    };
  },
};
</script>

<style scoped>
.all{
    display: grid;
    grid-auto-flow: column;
    background-color: bisque;
}
img{
    height: 300px;
    width: 300px;
}
</style>
