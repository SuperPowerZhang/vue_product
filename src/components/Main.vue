<template>
    <main>
        <div class="pro-list-head">
            <select>
                <option value="all">全部品类</option>
            </select>
            <input placeholder="搜索" v-model="searchItem" >

        </div>
        <div class="pro-list-body">
            <ul>
                <li class="pro-list-li pro-list-title">
                    <span class="id">ID</span>
                    <span class="name">产品名称</span>
                    <span class="type">品类</span>
                    <span class="size">型号</span>
                    <span class="entry">功能入口</span>
                    <span class="actions">操作xxx</span>
                </li>
                <li v-for="item in productList" :key="item.id">
                    <span class="id">{{item.id}}</span>
                    <span class="name"><a src="">{{item.name}}</a></span>
                    <span class="type">{{item.type}}</span>
                    <span class="size">{{item.size}}</span>
                    <span class="entry">{{item.entry}}</span>
                    <span class="actions">操作xxx</span>
                </li>
            </ul>
        </div>
    </main>
</template>

<script>
    export default {
        name: "Main",
        data(){
            const searchItem="";
            const productList=[{
                id:"0098",
                name:"电压力锅 一锅双胆 一键排压 精准控温",
                type:"电压力锅",
                size:"CYSB50YCW10DJ-100",
                entry:'5',
            },{
                id:"0097",
                name:"电压力锅 一锅双胆 一键排压 精准控温 304不锈钢智...",
                type:"电压力锅",
                size:"CYSB50YCW10DJ-100",
                entry:'5',
            },
            ]
            return{searchItem,productList}
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
        >.pro-list-body{
            li{
                border-top:1px solid rgb(241, 244, 246);
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
                >span{
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