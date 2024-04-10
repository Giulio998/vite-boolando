<script>
export default {
  props: {
    brand: String,
    firstImage : String,
    secondImage : String,
    price : Number,
    discount : Number,
 
  },
  data(){
    return {
        hovered: false,
    }
  },
  methods: {
    discountedPrice(price,discount){
        return (price - (price*discount / 100)).toFixed(2)
    }
  },
}
</script>

<template>
    <div class="col-4">
        <div @mouseover="hovered = true" @mouseleave="hovered = false" class="card ">
            <div class="cardHead">
                <div class="prodotto">
                    <img class="cardImg" :src="hovered ? secondImage : firstImage ">

                </div>
                <span class="red badge">{{discount}}%</span>
                <span class="preferiti badge">&hearts;</span>
                <span class="green badge">Sostenibilità</span>
            </div>
            <div class="cardInfo">
                <span class="brand">{{ brand }}</span>
                <h5>RELAXED FIT TEE UNISEX</h5>
                <span class="prezzoScontato marginRight">{{discountedPrice(price,discount)}}</span>
                <span><del>{{ price }}</del></span> 
            </div>

        </div>
    </div>
</template>

<style scoped>
.card{
    height: 500px;
    width: 277px;
}

.cardHead{
    position: relative;
    height: 400px;
}


.prezzoScontato{
    color: red;
}

.brand{
    font-size: small;
}

.badge{
  
    padding: 5px 10px 5px 10px;
    position: absolute;
    z-index: 3;
    
}

.red{
    left: 0px;
    bottom: 35px;
    background-color: red;
    color: white;
}

.green{
    background-color: green;
    left: 55px;
    bottom: 35px;
    color: white;
}

.customGreen{
    background-color: green;
    left: 0px;
    bottom: 35px;
    color: white;
}

.preferiti{
    right: 0px;
    top: 15px;
    font-size:large;
    background-color: white;

}

.prodotto{
   height: 100%;
   position: relative;
}


.cardImg{
    height: 100%;
}

.preferiti:hover.preferiti{
    color: red;
}

</style>