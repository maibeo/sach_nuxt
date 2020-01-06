<template>
    <div class="book-detail">
        <div class="container">
            <div class="row">
                <div class="col-md-9">
                    <div style=" border: 1px solid #e4e4e4;margin: 15px 0">
                        <div class="info-book">
                            <div class="row">
                                <div class="col-md-4">
                                    <div class="images">
                                        <img :src="bookPost.images" alt="" class="img-fluid">
                                    </div>
                                </div>
                                <div class="col-md-8">
                                    <div class="text">
                                        <h4>{{bookPost.name}}</h4>
                                        <p>Tác giả : <span>{{bookPost.actor}}</span></p>
                                        <p>Thể loại : <a href="#">{{bookPost.type_book}}</a></p>
                                        <p>Nguồn: <span>{{bookPost.copy_by}}</span></p>
                                        <a href="#" class="btn btn-read">Đọc ngay</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <ListChapter :bookPost="bookPost"/>
                    </div>
                </div>
                <div class="col-md-3">
                    <Right/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Right from "../../../components/right";
    import ListChapter from "../../../components/listChapter";

    export default {
        name: "Detail",
        components: {ListChapter, Right},

        data() {
            return {
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
                            },
                            {
                                id: 2,
                                name: 'Chương 1',
                                title: 'sgfshgd',
                            },
                            {
                                id: 3,
                                name: 'Chương 1',
                                title: 'sgfshgd',
                            },
                            {
                                id: 4,
                                name: 'Chương 1',
                                title: 'sgfshgd',
                            },
                            {
                                id: 5,
                                name: 'Chương 1',
                                title: 'sgfshgd',
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
                            },
                            {
                                id: 2,
                                name: 'Chương 1bfg',
                                title: 'sgfshgd',
                            },
                            {
                                id: 3,
                                name: 'Chương 1kjjh',
                                title: 'sgfshgd',
                            }
                        ],
                    },
                ]
            }
        },
        computed: {
            bookPost: function () {
                return this.infoBook.find(el => el.id.toString() === this.id);
            },
        },
        methods: {},
        mounted() {
        }
    }
</script>

<style scoped lang="scss">
    .book-detail {
        .info-book {
            margin: 15px;

            .images {
                height: 200px;
                width: 90%;
                text-align: center;
                margin: auto;

                img {
                    width: 100%;
                    height: 100%;
                    object-fit: cover;
                }
            }

            .btn-read {
                background-color: #3b8070;
                padding: 5px 20px;
                color: #ffffff;
            }
        }
    }

    /*@import "";*/
</style>