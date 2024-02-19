<script>
    export default{
        name: "Courses",
        props:{
            propsElement: Object
        }
    }
</script>

<template>

    <div class=" border">
        <figure>
            <img :src="'./img/'+ propsElement.img" alt="" class="w-100">
        </figure>

        <span class="text-secondary px-3">{{ propsElement.genre }}</span>
        <p class="px-3 mt-3">{{ propsElement.paragraph }}</p>
        <hr class="mx-3">

        <div class="px-3 d-flex align-items-center justify-content-between"> 
            <div class="d-flex ">
                <i class="fa-solid fa-star text-warning"></i>
                <i class="fa-solid fa-star text-warning"></i>
                <i class="fa-solid fa-star text-warning"></i>
                <i class="fa-solid fa-star text-warning"></i>
                <i class="fa-regular fa-star text-warning"></i>
            </div>

            <div>
                <span id="cancelPrice" class="d-block text-secondary text-decoration-line-through">{{ propsElement.fullPrice }}</span>
                <span id="price" class="text-bold text-">{{ propsElement.price }}</span>
            </div>

        </div>
    </div>

</template>

<style lang="scss" scoped>
    div{
        flex-basis: calc(100% / 6 - 20px);
    }

    #cancelPrice{
        font-size: 12px;
    }

    #price{
        font-size: 18px;
    }

</style>