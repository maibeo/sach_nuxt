<template>
    <div class="page-detail">
        <div class="container">
            <div class="head">
                <h3>{{infoBook.name}}</h3>
                <p>{{Chapter.name}}: {{Chapter.title}} </p>
            </div>
            <div class="chapter-text">
                <div class="next-chap">
                    <button class="btn btn-back">Quay lại</button>
                    <button class="btn btn-next">Tiếp theo</button>
                </div>
                <div class="text" v-html="Chapter.content">
                </div>
                <div class="next-chap">
                    <button class="btn btn-back">Quay lại</button>
                    <button class="btn btn-next">Tiếp theo</button>
                </div>
            </div>
            <list-chapter/>
        </div>
    </div>
</template>

<script>
    import ListChapter from "../../components/listChapter";
    export default {
        name: "PageDetail",
        components: {ListChapter},
        data(){
            return{
                Chapter:{
                    id:'1',
                    name:'Chương 1',
                    title:'sgfshgd',
                    content:'<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                        '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                        '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                        '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>'
                },
                infoBook:{
                    id:1,
                    name:'hfdf',
                    actor:'hfd',
                    type_book:'truyện',
                    copy:'sách vui',
                    image:'images/img1.jpg'
                }
            }
        },
        methods:{
            next(){

            }
        }
    }
</script>

<style scoped lang="scss">

</style>