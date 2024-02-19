<script>
  import Courses from './Courses.vue';

  export default{
    name: "AppMain",
    components:{
      Courses
    },
    data(){
      return{
        popularCourses: [
          {
            img: "246154_d8b0_3-272x161.jpg",
            genre:"Development",
            paragraph:"The Complete iOS 10 & Swift 3 Developer Course",
            stars: 4,
            fullPrice: "$199.99",
            price: "$100"
          },
          {
            img: "752950_b773-272x161.jpg",
            genre:"Development",
            paragraph:"The Complete iOS 10 & Swift 3 Developer Course",
            stars: 4,
            fullPrice: "$199.99",
            price: "$100"
          },
          {
            img: "895786_7b4b_2-272x161.jpg",
            genre:"Development",
            paragraph:"The Complete iOS 10 & Swift 3 Developer Course",
            stars: 4,
            fullPrice: "$199.99",
            price: "$100"
          },
          {
            img: "1253188_58f7_2-272x161.jpg",
            genre:"Development",
            paragraph:"The Complete iOS 10 & Swift 3 Developer Course",
            stars: 4,
            fullPrice: "$199.99",
            price: "$100"
          },
          {
            img: "951684_9c1a_2-544x322.jpg",
            genre:"Development",
            paragraph:"The Complete iOS 10 & Swift 3 Developer Course",
            stars: 4,
            fullPrice: "$199.99",
            price: "$100"
          },
          {
            img: "919872_ed54_6-272x161.jpg",
            genre:"Development",
            paragraph:"The Complete iOS 10 & Swift 3 Developer Course",
            stars: 4,
            fullPrice: "$199.99",
            price: "$100"
          },
        ]
      }
    }
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

    <div  class="mt-5 px-5">
      <h5 class="text-bold">Popular Development Courses</h5>

      <div id="containerCourse" class="d-flex flex-wrap justify-content-center mt-4">
        <Courses v-for="(element,index) in popularCourses" :propsElement="element" :key="index" />
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

    div{
      h5{
        padding-left: 10px;
      }

      #containerCourse{
        gap: 20px;
      }
    }


  }
</style>