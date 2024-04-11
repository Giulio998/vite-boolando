<script>

export default {
   
    props: {
        brand: String,
        frontImage: String,
        backImage: String,
        price: Number,
        name: String,
        badges: [Object],
        isInFavorites: Boolean,
    },
    data() {
        return {
            hovered: false,
        }
    },
    methods: {
    stringToNumber(var1){
       return parseInt(var1.replace('-',''))
        
    },
    discountedPrice(price,var1){
     return (price - ((this.stringToNumber(var1) * price) / 100)).toFixed(2)
    }

  },

}


</script>

<template>
    <div class="col-4">
        <div @mouseover="hovered = true" @mouseleave="hovered = false" class="card ">
            <div class="cardHead">
                <div class="prodotto">
                    <img class="cardImg" :src="hovered ? backImage : frontImage">
                    <template v-for="(badge, index) in badges" :key="index">
                        <span v-if="badge.type=='discount'" class="red badge firstBadge">{{ badge.value }}</span>
                        <span @click="isInFavorites = !isInFavorites"   :class=" isInFavorites ? 'favorite preferiti badge' : 'preferiti badge' "  >&hearts;</span>
                        <span v-if="badge.type=='tag' && badges.length > 1" class="green badge secondBadge">{{ badge.value }}</span>
                        <span v-else-if="badge.type=='tag'" class="green badge firstBadge">{{ badge.value }}</span>
                        
                    </template>
                </div>
            </div>
            <div class="cardInfo">
                <span class="brand">{{ brand }}</span>
                <h5>{{ name }}</h5>
                <template v-for="(badge, index) in badges" :key="index">
                    <span v-if="badge.type=='discount'" class="prezzoScontato marginRight">{{ discountedPrice(price, badge.value) }}</span>
                </template>
                
                <span><del>{{ price }}</del></span>
            </div>

        </div>
    </div>
</template>

<style scoped>
.card {
    height: 500px;
    width: 277px;
}

.cardHead {
    position: relative;
    height: 400px;
}


.prezzoScontato {
    color: red;
}

.brand {
    font-size: small;
}


.customGreen {
    background-color: green;
    left: 0px;
    bottom: 35px;
    color: white;
}



.prodotto {
    height: 100%;
    position: relative;
}


.cardImg {
    height: 100%;
}

.badge {

padding: 5px 10px 5px 10px;
position: absolute;
z-index: 3;

}

.firstBadge{
left: 0px;
bottom: 35px;
}

.secondBadge{
left: 55px;
bottom: 35px;
}

.red {
background-color: red;
color: white;
}

.green {
background-color: green;

color: white;
}


.favorite{
    color: red;
}

.preferiti{
    right: 0px;
    top: 15px;
    font-size:large;
    background-color: white;
    cursor: pointer;
}


</style>