<template>
    <div class="pro-list-body">
        <ul>
            <li class="pro-list-li pro-list-title">
                <div>
                    <span class="id">ID</span>
                    <span class="name">产品名称</span>
                    <span class="type">品类</span>
                    <span class="size">型号</span>
                    <span class="entry">功能入口</span>
                    <span class="actions">操作</span>
                </div>
            </li>
            <li v-for="item in products" :key="item.id">
                <Product :item="item" />
            </li>
        </ul>
    </div>
</template>

<script>
import Product from './Product.vue'
    export default {
        name: "Products",
        components:{
            Product
        },
        props:{
            products:{
                type:Array
            },
            test:{
                type:String
            }
        }
    }
</script>

<style >

</style>