<template>
    <div class="coach">
        <div class="coach__item">
            <p class="coach__title">What's New</p>
            <p class="coach__gretting">The Benefits of <br> Coaching</p>
            <div class="progress">
                <div class="progress__item" v-for="(item,index) in progressBars" :key="index">
                    <div class="progress__info">
                        <div class="progress__name">{{item.title}}</div>
                        <div class="progress__percent">{{item.count | percent}}</div>
                    </div>
                    <div class="progress__count">
                        <div class="progress__content">
                            <progress max="100" :value="item.count" class="progress__bar" height="50">
                            </progress>
                        </div>
                    </div>
                </div>    
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:'coach',
    data(){
        return{
            progressCount:-700,
            progressBars:[
                {
                    title:'Interior Design',
                    count:87,
                },
                {
                    title:'Architecture',
                    count:95,
                },
                {
                    title:'Urban Planning',
                    count:78
                }
            ]
        }
    },
    computed: {
        currentProgress(){
            return `transform:translateX(${this.progressCount}px)`;
        },
        currentCount(){
            return this.currentProgressCount
        },
    },
    filters:{
        percent(value){
            return value + '%'
        }
    }
}
</script>
<style lang="scss">
@import '../../../assets/Scss/mixins.scss';
    .coach{
        position: absolute;
        background-image: url('../../../assets/Img/pg2/h9-backgoround-7.png');
        background-size: cover;
        &__item{
            margin: 30% 0% 0% 20%;
        }
        &__title{
            margin:10px 0px;
            @include Text(#04D2C8,27px,600,0.02em);
            font-family: 'Crimson Text', serif;
        }
        &__gretting{
            margin:0px 0px 60px 0px ;
            @include Text(#171717,55px,600,0.02em);
        }
    }
    .progress{
        &__content{
            display: flex;
            width: 600px;
            height: 25px;
            position: relative;
            overflow: hidden;
        }
        &__main{
            width: 100%;
            background: rgb(255, 255, 255);
            height: 5px;
            position: absolute;
            z-index: 2;
        }
        &__line{
            width: 100%;
            background: rgb(253, 251, 251);
            height: 5px;
            z-index: 1;
        }
        &__info{
            max-width: 600px;
            display: flex;
            justify-content: space-between;
            @include Text(rgb(100, 94, 109),17px,400,0.02em);
            font-family: 'Crimson Text', serif;
            margin: 10px 0px;
        }
        &__bar{
            display: block;
            color: #fff;
            border:none;
            background: #dadada;
            box-sizing: border-box;
            width: 600px;
            height: 8px;
            line-height: 21px;
            font-size: 15px;
            font-family: sans-serif;
            text-align: center;
        }
    }
    ::-moz-progress-bar {
        background: #04D2C8;
    }
</style>