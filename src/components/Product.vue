<template>
    <div>
    <span class="id">{{item.id}}</span>
    <span class="name">
        <a src="">{{item.name}}</a>
        <span class="full">{{item.name}}</span>
    </span>
    <span class="type">{{item.type}}</span>
    <span class="size">{{item.size}}</span>
    <span class="entry">{{item.entry}}</span>
    <span class="actions">x x x</span>
    </div>
</template>

<script>
    export default {
        name: "Product",
        props:{
            item:{
                type:Object
            }
        },

    }
</script>

<style lang="scss">
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
    }
    span{
        display: inline-block;
        height: 35px;
        line-height: 35px;
        position: relative;
        margin-top: 0;
    &.id{
         width: 140px;
         line-height: 35px;
     }
    &.name{
         width: 400px;
         white-space: nowrap;
         text-overflow:ellipsis;
         overflow:hidden;
        position: relative;
        .full{
            border: 1px solid red;
            color: rgb(125, 134, 142);
            width: 240px;
            height: 48px;
            float: left;
            top: 39px;
            left: 150px;
        /*    display: none;*/
        }
    a {
        color: rgb(81, 169, 194);
    }

    &:hover{
         cursor:pointer;
        >.full{


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


</style>