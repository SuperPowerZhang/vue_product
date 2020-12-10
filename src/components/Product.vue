<template>
    <div>
    <span class="id">{{item.id}}</span>
    <span class="name"><a src="">{{item.name}}</a></span>
    <span class="type">{{item.type}}</span>
    <span class="size">{{item.size}}</span>
    <span class="entry">{{item.entry}}</span>
    <span class="actions">操作xxx</span>
    </div>
</template>

<script>
    export default {
        name: "Product",
        props:{
            item:{
                type:Object
            }
        }
    }
</script>

<style >

</style>