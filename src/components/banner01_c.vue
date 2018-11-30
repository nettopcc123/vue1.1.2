<template>
    <div>
        <div class="iftop">
        <iframe ref="iframe" id="bdIframe" :src="bdTokenUrl" frameborder="0" scrolling="no" width="100%" height="350px" ></iframe>
        </div>
        <vue-banner01></vue-banner01>
    </div>
</template>

<script>
import banner from './../components/banner';
import banner01 from './../components/banner01_b';
    export default {
        data() {
            return {
                bdTokenUrl: 'https://m.sporttery.cn/app/zf/fb/livelist.html'
            }
        },
        // created() {
        //     this.getUrl();
        //     this.$nextTick(()=>{
        //         this.getCode();
        //     });
        // },
        mounted(){
            /**
             * iframe-宽高自适应显示   
             */
            const oIframe = document.getElementById('bdIframe');
            const deviceWidth = document.documentElement.clientWidth;
            const deviceHeight = document.documentElement.clientHeight;
            oIframe.style.width =  '100%'; //数字是页面布局宽度差值
            oIframe.style.height = '350px'; //数字是页面布局高度差
        },
  components: {
    'vue-banner':banner,
    'vue-banner01':banner01,
  },
    //     methods: {
    //         /**
    //          * 获取-外部接口信息
    //          */
    //         getUrl() {
    //             let that = this
    //             let bdUrl = {queryurl: this.$paths.bdpath+'/locate'};
    //             this.$api.getBdToken(bdUrl,function(res) {
    //                 that.bdTokenUrl = res.data.data;
    //             })
    //         },
    //    }
    }
</script>

<style>
.child-view{
    height:100%
}
.iftop{
    margin-top:-1.1rem;
    height: 360px;
    position: relative;
    z-index: 0;
}
</style>
