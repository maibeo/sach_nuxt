<template>
    <div class="page-detail">
        <div class="container">
            <div class="head">
                <h3>{{bookPost.name}}</h3>
                <p>{{bookDetail.name}}: {{bookDetail.title}} </p>
            </div>
            <div class="chapter-text">
                <div class="next-chap">
                    <button class="btn btn-back" @click="back">Quay lại</button>
                    <button class="btn btn-next" @click="next">Tiếp theo</button>
                </div>
                <div class="text" v-html="bookDetail.content">
                </div>
                <div class="next-chap">
                    <button class="btn btn-back">Quay lại</button>
                    <button class="btn btn-next">Tiếp theo</button>
                </div>
            </div>
            <ListChapter :bookPost="bookPost"/>
        </div>
    </div>
</template>

<script>
    import ListChapter from "../../../../components/listChapter";
    export default {
        name: "index",
        components: {ListChapter},
        computed: {
            bookDetail: function () {
                // const id = this.infoBook.find(el => el.id == this.id);
                return this.bookPost.listChapter.find(el => el.id == this.chap);
            },
            bookPost: function () {
                return  this.infoBook.find(el => el.id == this.id);
            },
        },
        methods:{
        },
        data(){
            return{
                id: this.$route.params.id,
                chap: this.$route.params.chap,
                infoBook: [
                    {
                        id: 1,
                        name: 'tests',
                        images: '/images/img1.jpg',
                        actor: 'bfgf',
                        type_book: 'truyen',
                        copy_by: 'truyen',
                        listChapter: [
                            {
                                id: 1,
                                name: 'Chương 1',
                                title: 'chương 111',
                                content:'ghgsgd'
                            },
                            {
                                id: 2,
                                name: 'Chương 1',
                                title: 'sgfshgd',
                                content:'ghgsgd'
                            },
                            {
                                id: 3,
                                name: 'Chương 1',
                                title: 'sgfshgd',
                                content:'ghgsgd'
                            },
                            {
                                id: 4,
                                name: 'Chương 1',
                                title: 'sgfshgd',
                                content:'ghgsgd'
                            },
                            {
                                id: 5,
                                name: 'Chương 1',
                                title: 'sgfshgd',
                                content:'ghgsgd'
                            },
                        ],
                    },
                    {
                        id: 2,
                        name: 'tests12121',
                        images: '/images/img1.jpg',
                        actor: 'bfgf',
                        type_book: 'truyen',
                        copy_by: 'truyen',
                        listChapter: [
                            {
                                id: 1,
                                name: 'Chương 1 2222',
                                title: 'sgfshgd',
                                content:'<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>'
                            },
                            {
                                id: 2,
                                name: 'Chương 1bfg',
                                title: 'sgfshgd',
                                content:'<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>'
                            },
                            {
                                id: 3,
                                name: 'Chương 1kjjh',
                                title: 'sgfshgd',
                                content:'<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>\n' +
                                    '<p>"Nếu như số phận bắt buộc phải yêu em. Thì anh sẽ cam tâm tình nguyện tuân theo số phận đó"</p>'
                            }
                        ],
                    },
                ]
            }
        },
        methods:{
            next(){
                if(this.bookPost.listChapter.length > this.$route.params.chap){
                    this.chap = parseInt(this.chap) + 1;
                    this.$router.push({path: `/book-detail/${this.bookPost.id}/${this.chap}` });
                }
                else {
                    return;
                }
            },
            back(){
                if(1 < this.$route.params.chap){
                    this.chap = parseInt(this.chap) - 1;
                    this.$router.push({path: `/book-detail/${this.bookPost.id}/${this.chap}` });
                }
                else {
                    return;
                }
            }
        },
    }
</script>

<style scoped lang="scss">
    .page-detail{
        .head{
            margin-top: 10px;
            text-align: center;
            padding: 15px;
            background-color: #e5e5e5;
            p{
                margin-bottom: 0;
            }
        }
        .chapter-text{
            margin: 15px 0;
            background-color: #eee;
            .next-chap{
                text-align: center;
                padding: 25px 0;
                .btn{
                    background-color: #3b8070;
                    padding: 5px 15px;
                    color: #ffffff;
                }
            }
            .text{
                font-size: 20px;
                line-height: 20px;
                padding: 0 15px;
            }
        }
    }
</style>