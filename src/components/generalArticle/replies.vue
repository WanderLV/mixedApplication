<template>
	<section class="replies">
		
		<div class="weui-loadmore weui-loadmore_line">
            <span class="weui-loadmore__tips tipsText">华丽的分割线</span>
        </div>

        <div class="weui-panel weui-panel_access repliesweui-panel">
            <div class="weui-panel__hd repliesTitle">文章回复共 <yd-badge>{{repliesList_cont}}</yd-badge> 条</div>
            <div class="weui-panel__bd">
              

                <div class="weui-form-preview" v-for="item in repliesList">
                    <div class="weui-form-preview__hd">
                        <div class="weui-form-preview__item">
                            <div class="replies_imgHead"> 
                                <img :src="item.author.avatar_url">
                            </div>
                            <label class="weui-form-preview__label"><strong>{{item.author.loginname}}</strong> 说：</label>
                        </div>
                    </div>
                    <div class="weui-form-preview__bd">
                        <div class="weui-form-preview__item">
                            <span class="weui-form-preview__value" v-html="item.content">
                               
                            </span>
                        </div>
                    </div>
                </div>




               
            </div>
        </div>

	</section>
</template>

<script>
     export default {
        props:['repliesList'],
        mounted:function(){
            console.log(this.repliesList)
            this.repliesList_cont = this.repliesList.length
        },
        data(){
            return{
                repliesList_cont:''
            }
        },//data
        methods:{

        },
     }
</script>