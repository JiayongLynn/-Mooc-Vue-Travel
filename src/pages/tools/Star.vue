<template>
  <div class="Rating-gray">
            <span v-for="(item,index) in StarList" :key="index" class="fa" :class="item"></span>
  </div>
</template>

<script>
//星星长度
const LENGTH = 5;
//亮星
const CLS_ON = 'star_on';
//半星
const CLS_HALF = 'star_half';
//灰星
const CLS_OFF = 'star_off';
export default {
    name:'Star',
    props:{
        rating:{
            type:Number,
            default:5
        }
    },
     computed:{
        StarList(){
        
            let result = [];
            //对分数进行处理
            let score = Math.floor(this.rating*2)/2;
            // 控制半星
            let hasDecimal = score % 1 !== 0;
            // 全星
            let integer = Math.floor(score);
            // 全星放入到数组中
            for (let i = 0; i < integer; i++) {
                result.push(CLS_ON);
            }
            // 半星
            if (hasDecimal) {
                result.push(CLS_HALF);
            }
            // 补齐
            while (result.length < LENGTH) {
                result.push(CLS_OFF);
            }
        
            return result;

        }
    }
}
</script>

<style scoped>
    .Rating-gray {
        display: inline-block;
    }
    .fa{
        display:inline-block;
        background-repeat: no-repeat;
        width: 13px;
        height: 13px;
        margin-right :5px;
        background-size :13px 13px;
    }
    .star_on{
        background-image: url('../../assets/image/full.png');
    }
    .star_half{
        background-image: url('../../assets/image/half.png');
    }
    .star_off{
        background-image: url('../../assets/image/empty.png');
    }
</style>