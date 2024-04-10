<script>

</script>

<template>
  <header>
    <div class="container  whiteFont">
      <div class="row ">
        <div class="col-4 alignCenter"> 
          <ul class="alignCenter">
            <li class="marginRight"><a href="#">Donna</a></li>
            <li class="marginRight"><a href="#">Uomo</a></li>
            <li class="marginRight"><a href="#">Bambino</a></li>
          </ul>
        </div>
        <div class="col-4 flexCenter">
          <img class="logo" src="../assets/boolean-logo.png" alt="">
        </div>
        <div class="col-4 alignCenter">
          <ul class="alignCenter">
            <li class="marginLeft"><a href="#"><img class="icon" src="../assets/heart-solid.svg" alt=""> </a></li>
            <li class="marginLeft"><a href="#"><img class="icon" src="../assets/user-solid.svg" alt=""></a></li>
            <li class="marginLeft"><a href="#"><img class="icon" src="../assets/bag-shopping-solid.svg" alt=""></a></li>
          </ul>
        </div>     
      </div>
    </div>

  </header>
</template>

<style scoped>
header{
    position: fixed;
    z-index: 4;
    background-color: orange;
    width: 100%;
}

header .col-4:last-child{
    justify-content: flex-end;
}
.logo{
    height: 30px;
}

header .col-4 {
    height: 70px;
}
.icon{
    width: 20px;
}


</style>
