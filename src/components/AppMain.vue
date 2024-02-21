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
            paragraph:"Web Design for Beginners: Real World Coding in HTML & CSS ",
            stars: 4,
            fullPrice: "$129.99",
            price: "$65"
          },
          {
            img: "752950_b773-272x161.jpg",
            genre:"Development",
            paragraph:"GitHub Ultimate: Master Git and GitHub - Beginner to Expert",
            stars: 4,
            fullPrice: "199.99",
            price: "$50"
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
            paragraph:"Android Java Masterclass - Become an App Developer",
            stars: 4,
            fullPrice: "$99.99",
            price: "$50"
          },
          {
            img: "919872_ed54_6-272x161.jpg",
            genre:"Development",
            paragraph:"Xamarin Forms: Build Native Cross-platform Apps with C#",
            stars: 4,
            fullPrice: "$189.99",
            price: "$95"
          },
          {
            img: "186792_41e4_4-272x161.jpg",
            genre:"Arts & Crafts",
            paragraph:"Become an Arabic Calligraphy Artist from Scratch",
            stars: 4,
            fullPrice: "",
            price: "$199.99"
          },
          {
            img: "1208228_d61c_4-272x161.jpg",
            genre:"Design",
            paragraph:"Digitally Painting Light and Color: Amateur to Master",
            stars: 4,
            fullPrice: "$139.99",
            price: "$70"
          },
          {
            img: "1776542_30b1-272x161.jpg",
            genre:"Google",
            paragraph:"Google Searching Ninja!",
            stars: 4,
            fullPrice: "$99.99",
            price: "$45"
          },
          {
            img: "1561458_7f3b-272x161.jpg",
            genre:"Design",
            paragraph:"CSS - The Complete Guide 2020 (incl. Flexbox, Grid & Sass)",
            stars: 4,
            fullPrice: "$199.99",
            price: "$100"
          },
          {
            img: "366802_6fcc-272x161.jpg",
            genre:"Food & Beverage",
            paragraph:"Get Wine-Smart",
            stars: 4,
            fullPrice: "$49.99",
            price: "$25"
          },
          {
            img: "1414956_d944_15-272x161.jpg",
            genre:"Arts & Crafts",
            paragraph:"Mastering Brushstrokes - Part 1",
            stars: 4,
            fullPrice: "$19.99",
            price: "$10"
          },
        ],
        menuCourses: [
          { id: 1, name: 'All Categories',  active: false },
          { id: 2, name: 'Business',  active: false },
          { id: 3, name: 'Development',  active: false },
          { id: 4, name: 'Design',  active: false },
          { id: 5, name: 'IT & Software',  active: false },
          { id: 6, name: 'Lifestyle',  active: false },
          { id: 7, name: 'Marketing',  active: false },
          { id: 8, name: 'Office Productivity',  active: false }
        ],
        selectedMenuId: null,
        isHidden: false
      }
    },
    methods:{
      activeMenu(menuId){
        this.selectedMenuId = menuId;
      },
      loadMore(){
        this.isHidden = true      
      }
    }
  }
</script>

<template>
  <main>
    <!-- JumboTron -->
    <div id="jumboTron" class="">
      <div id="leftJumbo" class="col-xl-6 col-lg-8 col-md-7 col-sm-7 ">
        <h1>Udemy Affiliate Sales</h1>
        <p class="fs-5">
          Monetize your audience and attract new customers with Udemy!
        </p>
      </div>

      <div class="position-relative col-xl-6 col-lg-4 col-md-5">
        <img src="/img/slide-1.jpg" alt="" width="">

        <div class="triangle-left"></div>
      </div>
    </div>

    <!-- Courses -->
    <div  class="mt-5 px-xl-5 px">
      <h5 class="text-bold">Popular Development Courses</h5>

      <div class="d-flex flex-wrap justify-content-center mt-4 mb-5 containerCourse">
        <Courses v-for="(element,index) in popularCourses.slice(0, 6)" :propsElement="element" :key="index" />
      </div>
    </div>

    <!-- JumboTron 2 -->
    <div id="bg-image" class="d-flex flex-column ">
      <h2>Limitless learning,  more possibilities</h2>
      <p>Online courses open the opportunity for learning to almost anyone, regardless of their scheduling commitments</p>
      <div>

        <button id="signUp" class="px-4 py-3 rounded-pill border border-none">
          READ MORE
        </button>
      </div>
    </div>

    <!-- Courses Recenet -->
    <div>
      <h1 class="text-center mt-5 text-bold">Recent Courses</h1>

      <ul class="d-flex flex-wrap gap-3 justify-content-center mt-5 ">
        <li 
        class="menu-item" 
        v-for="(element, index) in menuCourses" 
        :key="element.id" 
        :class="{'active' : element.id === selectedMenuId}" 
        >

          <a 
          class="text-secondary" 
          @click="activeMenu(element.id)"
          >

            {{ element.name }}
          </a>
        </li>
      </ul>

      <div class="d-flex flex-wrap justify-content-center mt-5 mb-4 containerCourse px-xl-5 px-lg-1">
        <Courses v-for="(element,index) in popularCourses" :propsElement="element" :key="index" />



        <Courses v-show="isHidden" v-for="(element,index) in popularCourses" :propsElement="element" :key="index" />

        <button class="px-4 py-3 rounded-pill border border-none mt-4" @click="loadMore()" v-show="!isHidden">
          LOAD MORE
        </button>
      </div>

    </div>

    <!-- NewsLetter -->
    <div id="newsLetter" class="d-flex flex-column flex-lg-row justify-content-center gap-4 align-items-center">
      <div id="leftMail"> 
        <h5>Subscribe our newsletter</h5>
        <p>
          There are many variations of passages of Lorem Ipsum available, but the majority have <br> suffered alteration in some form, by injected humour, or randomised words
        </p>
      </div>

      <div id="rightMail" >
        <span>YOUR EMAIL ADDRESS</span>
        <div >
          <input type="email" placeholder="Enter your email">
          <button class="">SUBSCRIBE</button>
        </div>
      </div>
    </div>

      <!-- Courses Populari -->
    <div id="popularCourses">
      <h1 class="text-center text-bold pt-3">Popular Courses</h1>
      <p class="text-center">Discover our most popular courses for self learning</p>

      <div class="d-flex flex-wrap justify-content-center mt-5 mb-4 containerCourse px-xl-5 px-lg-1">
        <Courses v-for="(element,index) in popularCourses" :propsElement="element" :key="index" class="bg-white singleCourse" />
      </div>

      <div class="mt-5 d-flex justify-content-center">
          <i class="fa-solid fa-chevron-left bg-white border p-2 px-3"></i>
          <i class="fa-solid fa-chevron-right bg-white border p-2 px-3"></i>
        </div>
    </div>
    
    <!-- Become Instructor & Access For Business -->
    <div id="ctaSection" class=" d-flex flex-lg-row flex-column justify-content-center gap-5 px-5">
      <div class="card d-flex align-items-center p-5 gap-4">
        <figure>
          <img src="/img/image_box_1-221x231.png" alt="">
        </figure>

        <div class="">
          <h3>Become an Instructor</h3>
          <p>Teach What you love. Masterstudy gives you the tool to create a course.</p>
          <button class="px-4 py-3 rounded-pill border border-none">START TEACHING</button>
        </div>

      </div>

      <div  class="card d-flex align-items-center p-5 gap-4 ">
        <figure>
          <img src="/img/image_box_2-234x231.png" alt="">
        </figure>

        <div class="">
          <h3>Acces For Business</h3>
          <p >Get unlimited access to 2,500 of top courses for yout team.</p>
          <button class="px-4 py-3 rounded-pill border border-none">DOING BUSINESS</button>
        </div>

      </div>
    </div>

    <!-- Testimonials -->
    <div id="testimonials" class="d-flex justify-content-center">
      <div class="">
        <h2>Investing for Your Future</h2>
        <p class="text-secondary mb-4">
          It Is no exaggeration to say this MasterStudy experience was transformative-both professionally and personally. This workshop wil long remain a high point of my Ife. Thanks again... I am feeling energized and eager to start teaching my class next week. I can't wait to use all of my new teaching tcols. I will absolutely recommend this workshop to other educators!
        </p>

        <span class="d-block text-bold fs-5">Linda Green</span>
        <span class="text-secondary">Product Manager, Apple Inc</span>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
  
  main{
    // General
    a{
      text-decoration: none;
      cursor: pointer;
    }
    .active{
      background-color: #F0F4FA;
      border-radius: 100px;
    }
    button{
      background-color: #FF4450 ;
      color: white;
      font-weight: 500;
    }
    h1{
      font-size: 50px;
    }


    // JumboTron
    #jumboTron{
      background-color: #FF4450;
      margin-top: 30px;
      color: white;
      display: flex;
      justify-content: space-between;
      align-items: center;
      overflow: hidden;
      
      #leftJumbo{
        padding-inline: 100px;

        h1{
          font-weight: bolder;
        }
      }

      .triangle-left{
        width: 0;
        height: 0;
        border-top: 500px solid transparent;
        border-bottom: 200px solid transparent;
        // border-right: 600px solid white; 
        border-left: 200px solid #FF4450; 
        position: absolute;
        left: 0;
        top: 0;
      }


    }

    // Courses 1
    div{
      h5{
        padding-left: 10px;
      }

      .containerCourse{
        gap: 20px;
      }
    }

    // JumboTron 2
    #bg-image{
      background-image: url('./img/bg.png');
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
      padding-block: 150px;
      padding-inline: 150px;

      h2{
        font-size: 45px;
        font-weight: bold;
      }

      p{
        font-size: 18px;
        margin-bottom: 50px;
      }
    }

    // Courses Recent
    .menu-item {
      padding: 10px;
      border-radius: 100px;
    }




    // NewsLetter
    #newsLetter{
      background-color: #FF4450;
      padding-block: 40px;
      color: white;
      button{
        background-color: #457992;
        border: none;
        padding: 10px;
      }
      input{
        padding-block: 10px;
        padding-inline: 5px;
        border: none;
      }
      p{
        padding-inline: 10px;
      }
    }

    // Popular Course
    #popularCourses{
      background-color: #F0F4FA;
      padding-block: 100px;
      .containerCourse{
        .singleCourse:nth-child(n+5){
          display: none;
        }
      }
      
    }

    // Cta Section
    #ctaSection{
      padding-block: 100px;
      button{
        font-size: 14px;
      }
      
      .test{
        border: 4px solid green;
      }

      h3{
        font-size: 35px;
        font-weight: bold;
      }

      p{
        
      }
    }

    #testimonials{
      background-image: url('/img/testimonial-1-1917x640-1-1914x639.jpg');
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
      padding-block: 200px;
      

      div{
        background-color: white;
        padding-block: 100px;
        padding-inline: 50px;
        // p{
          
        // }

        h2{
          font-size: 40px;
          margin-bottom: 30px;
        }
        
      }
      
    }

  }

  // LG
  @media screen and (max-width: 1024px) {
    main{
      #jumboTron{
        height: 350px;

        #leftJumbo{
          padding-inline: 30px;
        }
      }

      #bg-image{
        padding-block: 100px;
        padding-inline: 20px;
        background-size: auto;


        h2{
          font-size: 45px;
          font-weight: bold;

        }

        p{
          font-size: 25px;
          margin-bottom: 50px;
          margin-top: 20px;
        }
      }

      #popularCourses .containerCourse .singleCourse:nth-child(n+5){
        display: none;
      }
      
    }
  }
  
  // MD
  @media screen and (max-width: 768px) {
    main #popularCourses .containerCourse .singleCourse:nth-child(n+3){
        display: none;
      }
  }


  // SM
  @media screen and (max-width: 425px) {
    main #popularCourses .containerCourse .singleCourse:nth-child(n+2){
        display: none;
      }
    

  }
</style>