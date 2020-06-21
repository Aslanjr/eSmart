<template>
    <div class="sarah" @click="scroll">
        <transition name="AnimeUp">
            <div class="sarah__item" id="fp-page" v-show="fpPage"></div>
        </transition>
        <transition name="AnimeDown"><div class="sarah__item" id="fp-page" v-show="fpPage">
            <p class="sarah__title">Your Coach</p>
            <p class="sarah__greeting">Hello, I'm <br> Sarah</p>
            <p class="sarah__text">Lorem ipsum dolor sit amet, consectetur adipi scing elit. <br>
                 Maecenas vehicula condimentum arcu sit amet varius. <br> Ut ac consectetur tortor.
            </p>
            <button class="sarah__btn">Sign Up Now!</button>
        </div>
        </transition>
        <transition name="AnimeDown"><Coach class="fp sarah__item" v-show="scPage" /></transition>
        <transition name="AnimeUp">
            <Img class="sc sarah__item" v-show="scPage" />
        </transition>
    </div>
</template>
<script>
import Coach from '../../components/Content/sc-page/coach'
import Img   from '../../components/Content/sc-page/img'

export default {
    name:'Sarah',
    data(){
        return{
            fpPage:true,
            scPage:false
        }
    },
    mounted() {
        window.addEventListener('wheel',()=>{
            console.log('whell');
            if(this.fpPage == true){
                this.scPage = true ;
                this.fpPage = false;
            }else{
                this.scPage = false ;
                this.fpPage = true;
            }
            
        })
    },
    methods: {
        scroll(){
            this.fpPage = true;
            this.scPage = false;
        }
    },
    components:{
        Coach,
        Img
    }
}
</script>
<style lang="scss">
@import '../../assets/Scss/mixins.scss';

    .sarah{
        display: flex;
        position: relative;
        &__item{
            position: absolute;
            width: 100vh;
            height: 100vh;
            flex-basis: 50%;
        }
        &__title{
            margin: 0% 13%;
            @include Text(#04D2C8,22px,600,0.02em)
        }
        &__greeting{
            margin: 1% 13%;
            @include Text(#42495B,92px,600,0.02em);
            line-height: 90px;
        }
        &__text{
            margin: 0% 13%;
            @include Text(#56575c,18px,500,0.05em);
            line-height: 28px;
        }
        &__btn{
            @include btn;
            @include Text(#fff,13px,700,0.05em);
            margin: 2% 13%;
        }
        &__item:nth-child(1){
            left:0%;
            background-image: url('../../assets/Img/h9-background-1.jpg');
            background-size: cover;
        }
        &__item:nth-child(2){
            left:50%;
            background-image: url('../../assets/Img/h9-backgoround-8.png');
            background-size: cover;
            padding:15% 0%;
        }
    }
    .AnimeUp-enter-active{
        animation: AnimeUp .45s ease-in-out;
    }
    .AnimeUp-leave-active{
        animation: AnimeUp .45s ease-in-out reverse;
    }
    @keyframes AnimeUp {
        0%{
            transform: translateY(-100vh);
        }
        100%{
        }
    }
    .AnimeDown-enter-active{
        animation: AnimeDown .45s ease-in-out;
    }
    .AnimeDown-leave-active{
        animation: AnimeDown .45s ease-in-out reverse;
    }
    @keyframes AnimeDown {
        0%{
            transform: translateY(100vh);
        }
        100%{
        }
    }
</style>