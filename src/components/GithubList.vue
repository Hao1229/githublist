<template>
  <div class="p-3">
     <div class="container">
       <div class="parallaxImg1 d-flex justify-content-center align-items-center">
         <div class="topicTitle">
           <span class="h1 text-danger font-weight-bold">Github List</span>
         </div>
       </div>
      <list-detail/>
     </div>
  </div>
</template>

<script>
import ListDetail from './ListDetail.vue'
export default {
  components: {
    ListDetail
  }
}
</script>

<style lang="scss" scoped>
.parallaxImg1{
  background-attachment: fixed;
  background-image: url('https://images.unsplash.com/photo-1463725876303-ff840e2aa8d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1189&q=80');
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  width: 100%;
  height: 500px;
}
.topicTitle{
  background-color: rgba($color: #dcdcdc, $alpha: 0.7);
  padding: 100px 100px;
}
</style>
