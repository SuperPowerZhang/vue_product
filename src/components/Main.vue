<template>
    <main>
        <div class="pro-list-head">
            <select>
                <option value="all">全部品类</option>
            </select>
            <input placeholder="搜索" v-model="searchItem" >
        </div>
        <Products :products="productsDisplay"  test="1111"/>
        <Notes :num="productListLength"  :noteNumber="noteNumber"/>
    </main>
</template>

<script>
    import Products from "./Products";
    import Notes from './Notes.vue'
    export default {
        name: "Main",
        components: {Products,Notes},
        props:{
            productList:{
                type:Array
            }
        },
        data(){
            const searchItem="";
            const displayType="";
            const noteNumber=10;
            return{searchItem,displayType,noteNumber}
        },
        computed:{
            productsDisplay:function(props){
                return props.productList
            },
            productListLength:function() {
                return this.productsDisplay.length
            }
        }
    }
</script>

<style lang="scss">
    $margin:15px;
    main{
        max-width: 1280px;
        margin:$margin;
        background-color: rgb(255, 255, 255);
        color:rgb(136, 145, 153);
        >.pro-list-head{
            display: flex;
            height: 50px;
            justify-content: flex-end;
            margin-right: 16px;
            align-items:center ;
            border-radius: 2px;

            >select{
                width: 95px;
                height: 32px;
                border: 1px solid rgb(222, 226, 230);
                color:rgb(136, 145, 153);
                padding-left: 8px;
            }
            >input{
                width: 200px;
                height: 32px;
                border: 1px solid rgb(222, 226, 230);
                padding-left: 15px;
                margin-left: 8px;
            }
        }
         .pro-list-body{
            li div{
                border-bottom:1px solid rgb(241, 244, 246);
                display: flex;
                justify-content: space-between;
                height: 36px;
                line-height: 36px;
                border-radius: 2px;
                padding-left: 16px;
                padding-right: 16px;
                >&.pro-list-title{
                        font-weight: 600;
                }
                span{
                    display: inline-block;
                    &.id{
                        width: 140px;
                    }
                    &.name{
                        width: 200px;
                        overflow: hidden;
                        >a{
                            color:rgb(81, 169, 194)
                        }
                    }
                    &.type{
                        width: 175px;
                    }
                    &.size{
                        width: 240px;
                    }
                }
            }
        }
    }

</style>