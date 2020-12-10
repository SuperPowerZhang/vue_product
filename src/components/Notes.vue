<template>
    <div class="pro-note">
        <span class="pro-note-all">共{{num}}条记录</span>
        <span class="pro-note-select" >
            <select>
                <option :value="noteNumber"></option>
            </select>
            条/页
        </span>
    </div>
</template>

<script>
    export default {
        name: "Notes",
        props:{
            num:{
                type:Number
            },
            noteNumber: {
                type:Number
            }

        }

    }
</script>

<style  lang="scss">
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

    }

}
</style>