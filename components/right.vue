<template>
    <div class="right">
        <h3 class="bg-info">Thể loại</h3>
        <ul>
            <li v-for="(item,i) in Category" :key="i">
                <a href="#"><font-awesome-icon :icon="['fas', 'check']"  style="color: green"/> {{item.name}}</a>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "Right",
        data(){
            return{
                Category:[
                    {
                        id:'1',
                        name:'Truyện'
                    },
                    {
                        id:'2',
                        name:'Truyện'
                    },
                    {
                        id:'3',
                        name:'Truyện'
                    },
                ]
            }
        }
    }
</script>

<style scoped lang="scss">
    .right{
        border: 1px solid #e5e5e5;
        margin-top: 40px;
        h3{
            font-size: 18px;
            color: #ffffff;
            text-align: center;
            padding: 10px;
        }
        ul{
            padding: 0;
            li{

                display: block;
                padding: 5px 10px;
                a{
                    color: #000000;
                }
                &:hover{
                    background-color: #e5e5e5;
                }
            }
        }
    }
</style>