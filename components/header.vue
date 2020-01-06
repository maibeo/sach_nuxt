<template>
    <b-navbar  toggleable="lg" type="dark" variant="info">
        <div class="container">
            <b-navbar-brand href="#">Mai Beo</b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

            <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav>
                    <b-nav-item href="#">Trang chủ</b-nav-item>
                    <b-nav-item-dropdown right>
                        <!-- Using 'button-content' slot -->
                        <template v-slot:button-content>
                            <em>Thể loại</em>
                        </template>
                        <b-dropdown-item v-for="(item,i) in Category" :key="i">{{item.name}}</b-dropdown-item>
                    </b-nav-item-dropdown>
                    <b-nav-item href="#">Trang chủ</b-nav-item>
                </b-navbar-nav>

                <!-- Right aligned nav items -->
                <b-navbar-nav class="ml-auto">
                    <b-nav-form>
                        <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
                        <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
                    </b-nav-form>

                </b-navbar-nav>
            </b-collapse>
        </div>

    </b-navbar>
</template>

<script>
    export default {
        name: "Header",
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
    .navbar-dark .navbar-nav .nav-link{
        color: #ffffff;
        em{
            color: #ffffff;
            font-style: normal;
        }
    }
    .navbar-nav li{
        &:hover{
            .nav-link{
                color: #000000;
                em{
                    color: #000000;
                }
            }
        }
    }
    .dropdown-menu{
        li{
            border-bottom: 1px solid #e5e5e5;
        }
    }

</style>