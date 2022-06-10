<template>
    <div class="container">
        <h2> This is ShopDetail Page for Item {{this.$route.params.id}}.</h2>

        <div class="card mb-3" >
            <div class="row g-0">
                <div class="col-md-4">
                <img :src="product.image" class="img-fluid rounded-start w-60 p-3" alt="">
                </div>
                <div class="col-md-8">
                <div class="card-body">
                    <h5 class="card-title">{{product.category}}</h5>
                    <p class="card-text">{{product.description}}</p>
                    <p class="card-text"><small class="text-muted">${{product.price}}</small></p>
                </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    const axios = require('axios').default;
    export default {
        name: 'ShopDetailView',
        data(){
            return{
                product:Object,
            }
        },
        mounted(){
            this.getSingleProduct();
        },
        methods:{
            getSingleProduct(){
                let id= this.$route.params.id
                axios.get('https://fakestoreapi.com/products/'+id)
                    .then(response =>{
                        //console.log(response)
                        this.product = response.data
                    })
            }
        }
    }
</script>

<style>
</style>