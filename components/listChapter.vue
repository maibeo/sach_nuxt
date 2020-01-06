<template>
    <div class="list-chapter">
        <h3>Danh sách chương</h3>
        <div class="list">
            <ul>
                <li v-for="(item) in bookPost.listChapter">
                    <nuxt-link :to="'/book-detail/'+bookPost.id+'/'+item.id">{{item.name}} : {{item.title}}</nuxt-link>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: "listChapter",
        props:['bookPost'],
        data(){
            return{
            }
        },
    }
</script>

<style scoped lang="scss">
    .list-chapter{
        padding: 0 15px;
        h3{
            text-transform: uppercase;
            font-weight: normal;
            border-bottom: 1px solid #e5e5e5;
            padding: 15px 0;
            font-size: 18px;
        }
        .list{
            ul{
                padding-left: 0;
                li{
                    padding: 10px;
                    list-style: none;
                    border-bottom: 1px solid #e5e5e5;
                    a{
                        color: #337ab7;
                    }
                }
            }
        }
    }
</style>