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
        <Products :products="products"  />
        <div class="pro-note">
            <span class="pro-note-all">共{{productListLength}}条记录，当前为1-x条</span>
            <span class="pro-note-select" >
            <select @change="modifyNumber($event)">
                <option v-for="number in  numbers" :value="number" :key="number">{{number}}</option>
            </select>
            条/页，共{{pages}}页
        </span>
        </div>
    </main>
</template>

<script>
    import Products from "./Products";
    export default {
        name: "Main",
        components: {Products},
        props:{
            productList:{
                type:Array
            }
        },
        data(){
            const searchContent="";
            const displayType="全部品类";
            const noteNumber=10;
            const numbers=[10,20,100];
            const pageDisplay=1;
            const productsComputed=[];
            return{searchContent,displayType,noteNumber,numbers,pageDisplay,productsComputed}
        },
        computed:{
            productsDisplay:function(props){
                return this.contentFilter(this.typeFilter(props.productList))
            },
            productListLength:function() {
                return this.productsDisplay.length
            },
            products:function(){
                this.productsComputed=[]
                     this.productsDisplay.forEach((item,index)=>{
                        if(index<this.noteNumber){
                            console.log(item)
                            this.productsComputed.push(item)
                        }
                    })

                return this.productsComputed
            },
            productTypeList:function() {
                let typeList=[];
                this.productList.forEach((item)=>{
                    if(typeList.indexOf(item.type)===-1){
                        typeList.push(item.type)
                    }
                })
                return  typeList
            },
            pages:function () {
                return Math.ceil(this.productListLength/this.noteNumber)
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
            modifyNumber:function(e){
                this.noteNumber=e.target.value
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

        .pro-note{
            display:flex;
            justify-content: space-between;
            height: 40px;
            line-height: 40px;
            margin-left: 16px;
            margin-right: 16px;
            select{
                width: 50px;
                height: 25px;
                color: rgb(125, 134, 142);
                border: 1px solid rgb(222, 226, 230);

            }

        }

    }

</style>