<script>
  export default{
    name: "AppMain"
  }
</script>

<template>
  <main>
    <div id="jumboTron">
      <div id="leftJumbo" class="">
        <h1>Udemy Affiliate Sales</h1>
        <p class="fs-5">
          Monetize your audience and attract new customers with <br>Udemy!
        </p>
      </div>

      <div class="position-relative">
        <img src="../../public/img/slide-1.jpg" alt="" class="">

        <div class="triangle-up"></div>
      </div>
    </div>
  </main>
</template>

<style lang="scss">

  main{
    #jumboTron{
      background-color: #FF4450;
      margin-top: 30px;
      color: white;
      display: flex;
      justify-content: space-between;
      align-items: center;
      overflow: hidden;
      
      #leftJumbo{
        margin-left: 200px;

        h1{
          font-weight: bolder;
        }
      }

      .triangle-up{
        width: 0;
	      height: 0;
	      border-left: 200px solid transparent;
	      border-right: 200px solid transparent;
	      border-bottom: 400px solid #FF4450;
        position: absolute;
        z-index: 1;
        top: 0;
        left: -200px;
      }
    }
  }
</style>