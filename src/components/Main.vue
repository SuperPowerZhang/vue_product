<template>
    <main>
        <div class="pro-list-head">
<!--            v-model="displayType"-->
            <select name="selectType" @change="modifyType($event)"  >
                <option value="全部品类"  >全部品类</option>
                <option :value="type" v-for="type in productTypeList" :key="type">{{type}}</option>
            </select>
            <input placeholder="搜索"  @keyup.enter="modifySearchContent($event)">
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
            const searchContent="";
            const displayType="全部品类";
            const noteNumber=10;
            return{searchContent,displayType,noteNumber}
        },
        computed:{
            productsDisplay:function(props){
                return this.contentFilter(this.typeFilter(props.productList))
            },
            productListLength:function() {
                return this.productsDisplay.length
            },
            productTypeList:function() {
                let typeList=[];
                this.productList.forEach((item)=>{
                    if(typeList.indexOf(item.type)===-1){
                        typeList.push(item.type)
                    }
                })
                return  typeList
            }
        },
        methods:{
            modifyType:function (e) {
                this.displayType=e.target.value
            },
            modifySearchContent:function(e){
                this.searchContent=e.target.value
                console.log(this.searchContent)
            },
            typeFilter:function(list){
                if(this.displayType==="全部品类"){
                    return   list
                }else{
                    return  list.filter((item)=>{
                        return item.type===this.displayType
                    })
                }
            },
            contentFilter:function(list){
                let listDisplay=[]
                if(this.searchContent===""){
                    listDisplay=list
                }else{
                    list.forEach((item)=>{
                        for(let k in item){
                            if(item[k]===this.searchContent){
                                listDisplay.push(item)
                            }
                        }
                    })
                }
                return listDisplay;
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
                display: flex;
                justify-content: flex-start;
                border-bottom:1px solid rgb(241, 244, 246);
                height: 36px;
                line-height: 36px;
                border-radius: 2px;
                padding-left: 15px;
                padding-right: 40px;
                >&.pro-list-title{
                        font-weight: 600;
                    >.entry{
                        text-align: center;
                    }
                }
                span{
                    display: inline-block;
                    height: 35px;
                    line-height: 35px;
                    position: relative;
                    margin-top: 0;
                    &.id{
                        /*position: absolute;*/
                        /*top: 0;*/
                        width: 140px;
                        line-height: 35px;
                    }
                    /*1220-140*/
                    &.name{
                        width: 400px;
                        white-space: nowrap;
                        text-overflow:ellipsis;
                        overflow:hidden;
                        a{
                            color:rgb(81, 169, 194);
                            &:hover{
                             cursor:pointer;
                            }
                        }
                    }
                    &.type{
                        width: 175px;
                    }
                    &.size{
                        width: 240px;
                    }
                    &.entry{
                        width: 50px;
                        text-align: right;
                        margin-right: 120px;
                    }
                    &.actions{
                        width: 40px;
                    }

                }
            }
        }
    }

</style>