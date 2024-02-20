<script>
  export default{
    name: "AppFooter"
  }
</script>

<template>
  <footer >
    <div class="d-flex align-items-center justify-content-center gap-5">
      <div>
        <h5 class="mb-4">ABOUT</h5>
        <p>Sed nc els pellentesque, bon du ed.<br> hres sapien. Pelletesae oc lech.<br> consectetur vel rutrum eu um. <br>Mowrts ccurmsen eros eget <br>lomro posuere wiputate.</p>
      </div>

      <div>
        <h5 class="mb-4">CONTACT</h5>
        <p>USA, California 20, First Avenue, California</p>
        <span class="d-block">Tel: +1 212 458 900 32</span>
        <span class="d-block mb-4">Tel: +1 212 458 900 32</span>
        <span class="text-secondary">info@masterstudy.com</span>
      </div>

      <div>
        <h5 class="mb-4">SOCIAL NETWORK</h5>
      </div>

      <div>
        <img src="/img/Top-udemy-courses-90-percent-off.jpg" width="350" alt="">
      </div>
    </div>

    <hr>

    <div class="d-flex justify-content-center align-items-center gap-2 py-1">
      <img src="/img/footer-logo2x-50x56.png" alt="" width="25" >
      <span>Copyright @2020. Masterstudy. Theme by StylemixThemes</span>
    </div>
  </footer>

</template>

<style lang="scss">
  footer{
    background-color: #273044;
    color: white;
    padding-block: 10px;

    div:first-child{
      padding-block: 30px;
    }
  }
</style>