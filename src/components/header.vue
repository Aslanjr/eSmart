<template>
    <div class="header">
        <div class="header__item">
            <img src="../assets/logo.png" height="74" alt="">
        </div>
        <div class="header__item">
            <div class="icon">
                <span class="icon__item"></span>
                <span class="icon__item"></span>
                <span class="icon__item"></span>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'Header',
    data(){
        return{

        }
    }
}
</script>
<style lang="scss">
    .header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1% 2%;
    }
    .icon{
        display: flex;
        flex-direction: column;
        justify-content: center;
        justify-items: center;
        cursor: pointer;
        &__item{
            display: block;
            height: 3px;
            width: 30px;
            border-radius: 7px;
            background-color: #000;
            margin: 3px 0px;
            transition: all .25s ease-in-out;
        }
        &:hover &__item:nth-child(2){
            display: none;
        }
        &:hover &__item:nth-child(1){
            background: #09D2C9;
            transform: rotate(90deg);
            width: 29px;
            height: 4px;
        }
        &:hover &__item:nth-child(3){
            transform: translateY(-9px);
            background: #09D2C9;
            width: 29px;
            height: 4px;
        }
    }
</style>