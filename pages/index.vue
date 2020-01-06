<template>
    <div class="home-page">
        <div class="container">
            <div class="content">
                <div class="row">
                    <div class="col-md-9">
                        <div class="top">
                            <h3>Tất cả sách</h3>
                        </div>
                        <div class="row" >
                            <div class="col-md-3 col-6 col-sm-6" v-for="(item,i) in infoBook" :key="i">
                                <div class="item">
                                    <div class="images">
                                        <a href="#">
                                            <img :src="item.images" alt="" class="img-fluid">
                                        </a>
                                    </div>
                                    <div class="text">
                                        <nuxt-link :to="'/book-detail/'+item.id">{{item.name}}</nuxt-link>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-md-3">
                        <Right/>
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>

<script>
import Right from "../components/right";

export default {
  components: {
      Right,
  },
  data(){
        return{
            infoBook:[
                {
                    id: 1,
                    name:'tests',
                    images:'/images/img1.jpg',
                },
                {
                    id: 2,
                    name:'tests12121',
                    images:'/images/img1.jpg',
                },
            ]
        }
    }
}
</script>

<style lang="scss">
    @import "index.scss";
</style>
