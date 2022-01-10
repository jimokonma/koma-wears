<template>
<div class="featured">
    <div class="holder L">
    <div v-bind:key="product.id" v-for="product in products.slice(12,13)">
        <img v-bind:src="product.img" v-bind:alt="product.name">
        <h3 class="oldPrice">{{product.price*1.3}}</h3>
        <h3>{{product.price}}</h3>
    </div>
    </div>
    <div class="holder R">
    <div v-bind:key="product.id" v-for="product in products.slice(5,6)">
        <img v-bind:src="product.img" v-bind:alt="product.name">
       
        <h3>{{product.price}}</h3>
    </div></div>
</div>
</template>

<script>
export default {
    name: "Featured",
    props: ["products"],
}
</script>

<style scoped>
.featured{
    width: 100%;
    max-width: 780px;
    margin: 0px auto;
    display: flex;
    }
    .holder{
        width: 200px;
        }
        .L{
            flex: 1;
            background: #9DC79F;
            justify-items: center;
        }
        .L img{
            width: 200px;
            border-radius: 40%;
            }
       .holder.R img{
              width: 100%;

            }
        .R{
            flex: 1;
            margin: 0px;
            border: solid;
            
        }
        .R>.el{
            position: absolute;
            color: red;
        }
        

</style>
