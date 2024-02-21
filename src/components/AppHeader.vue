<script>
  export default{
    name: "AppHeader",

    data(){
        return{
            arrayMenu: [
                { label: 'Home', link: '#' },
                { label: 'Pages', link: '#' },
                { label: 'Course Formats', link: '#' },
                { label: 'Courses', link: '#' },
                { label: 'Demos', link: '#' }
            ],
            arraySocial: [
                { icon: 'fa-facebook', link: '#' },
                { icon: 'fa-twitter', link: '#' },
                { icon: 'fa-instagram', link: '#' },
                { icon: 'fa-linkedin', link: '#' },
                { icon: 'fa-google-plus-g', link: '#' } 
            ],
            arrayBottom: [
                { iconClass: 'fa-solid fa-chart-line me-2', label:  'Business' },
                { iconClass: 'fa-solid fa-palette me-2', label:  'Design' },
                { iconClass: 'fa-solid fa-gear me-2', label:  'Development' },
                { iconClass: 'fa-regular fa-face-smile me-2', label:  'Lifestyle' },
                { iconClass: 'fa-solid fa-print me-2', label: 'Office Productivity' } 
            ]
        }
    }
  }
</script>

<template>
    <header>
        <nav id="topNav" class="border-bottom d-flex justify-content-between px-3 px-lg-3 px-xl-5 ">
            <div class="d-md-block d-sm-none d-none">
                <select >
                    <option value="English">English</option>
                    <option value="Italian">Italian</option>
                    <option value="Dutch">Dutch</option>
                    <option value="French">French</option>
                </select>

                
            </div>
            
            <span class="d-sm-block d-md-none text-secondary">
                Menu
            </span>


            <div class="d-flex align-items-center gap-3">
                <ul class="d-flex gap-4 "> 
                    <li v-for="(element, index) in arrayMenu" class="d-sm-none d-md-block d-none">
                        <a :href="element.link">{{ element.label }}</a>
                    </li>
                </ul>

                <ul class="d-flex gap-3 fs-5">
                    <li v-for="(element, index) in arraySocial">
                        <a :href="element.link">
                            <i class="fa-brands" :class="element.icon"></i>
                        </a>
                    </li>

                </ul>
            </div>
        </nav>

        <nav id="middleNav" class="py-4 px-3 px-xl-5 ps-lg-3 pe-lg-3 pe-xl-5 d-flex align-items-center justify-content-between">
            <figure class="m-0">
                <img src="/img/MasterStudy.svg" alt="Logo">
            </figure>

            <div class="d-flex align-items-center d-none d-lg-flex">
                <i class="fa-solid fa-bars me-1"></i>
                <span class="d-none d-xl-block">CATEGORY</span>

                <div class="ms-3 wrap">
                    <div class="search">
                        <input type="text" class="searchTerm px-1 py-2 border" placeholder="Search courses">
                        <button type="submit" class="searchButton py-2 px-3 border">
                            <i class="fa fa-search"></i>
                        </button>
                    </div>
                </div>
            </div>

            <div class="d-flex align-items-center d-none d-lg-flex">
                <i class="fa-solid fa-bullhorn me-3 me-lg-1 me-md-3 me-1"></i>
                <span class="d-none d-lg-none d-xl-block me-3">Become an Instructor</span>

                <i class="fa-solid fa-briefcase me-1"></i>
                <span class="d-none d-lg-none d-xl-block ">For Enterprise</span>
            </div>

            <div class="d-flex align-items-center">
                <i class="fa-solid fa-magnifying-glass me-4 d-block d-md-block d-lg-none "></i>
                <i class="fa-regular fa-user  me-1"></i>
                <span class="d-none d-lg-none d-xl-block me-3">Log in</span>

                <button id="signUp" class="ms-3 me-3 px-4 py-3 rounded-pill border border-none d-none d-lg-flex">
                    Sign up
                </button>

                <i class="fa-regular fa-bookmark fs-4 d-none d-lg-flex"></i>
            </div>
        </nav>

        <nav id="bottomNav" class="d-flex justify-content-center py-4 d-none d-lg-flex  ">
            <ul class="d-flex gap-5 m-0">
                <li v-for="(element, index) in arrayBottom">
                    <i :class="element.iconClass"></i>
                    <span>{{ element.label }}</span>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss" scoped>

    header{
        #topNav{
            padding-top: 15px;

            select{
                color: grey;
                border: 1px solid lightgrey;
            }


            a{
                text-decoration: none;
                color: grey;
            }
        }

        #middleNav{
            color: grey;
            .wrap{
                .search{
                    input{
                        width: 450px;
                        background-color: #F0F2F5;
                    }

                    button{
                        background-color: #457992;
                        
                        i{
                            color: white;
                        }
                    }
                }
            }

            i{
                color: #457992;
            }

            #signUp{
                background-color: #FF4450;
                color: white;
                text-transform: uppercase;
                font-weight: bold;
            }
        }

        #bottomNav{
            color: white;
            background-color: #273044;
            font-weight: 300;
            font-size: 18px;
        }
    }

    @media screen and (max-width: 1440px) {
        header{
            #middleNav{
            color: grey;
            .wrap{
                .search{
                    input{
                        width: 200px;
                        background-color: #F0F2F5;
                    }

                    button{
                        background-color: #457992;
                        
                        i{
                            color: white;
                        }
                    }
                }
            }

            i{
                color: #457992;
            }

            #signUp{
                background-color: #FF4450;
                color: white;
                text-transform: uppercase;
                font-weight: bold;
            }
        }
        }
        
    }
</style>