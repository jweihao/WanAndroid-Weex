<template>
    <div class="wrapper">
        <div class="register">
            <div>
                <div class="toolbar-warpper">
                    <!-- <div class="title"> -->
                    <text class="toolbar-text">注册</text>
                </div>
                <div class="toolbar-leftimage-warpper">
                    <image class="toolbar-leftimage" @click="leftback" :src="getUrl('arrow_left.png')" />
                </div>
            </div>
            <input v-model="userName" type="text" class="input" @change="changeUserName" placeholder="用户名(英文、数字和_)" autofocus="false" value="" />
            <div style="height:1px;background-color:#A5A5A5" />
            <input v-model="phoneNumber" type="tel" class="input" @change="changePhoneNumber" placeholder="手机号" autofocus="false" value="">
            <div style="height:1px;background-color:#A5A5A5" />
            <input v-model="Email" type="email" class="input" @change="changeEmail" placeholder="邮箱" autofocus="false" value="">
            <div style="height:1px;background-color:#A5A5A5" />
            <input v-model="UserPassword" type="password" class="input" @change="changeUserPassword" placeholder="密码(至少8位)" autofocus="false" value="">
            <div style="height:1px;background-color:#A5A5A5" />
            <input v-model="ConfirmPassword" type="password" class="input" @change="changeConfirmPassword" placeholder="确认密码" autofocus="false" value="">
            <div style="height:1px;background-color:#A5A5A5" />
            <div class="code-warpper">
                <input v-model="IdentifyingCode" type="text" class="input" @change="changeIdentifyingCode" placeholder="验证码" autofocus="false" value="">
                <text class="code-text" @click="getiphonecode">获取验证码</text>
            </div>
            <div style="height:1px;background-color:#A5A5A5" />
            <div class="agree-warpper">
                <image class="agree-img" @click="agree" :src="getUrl('select2_normal.png')" />
                <text class="agree-text">同意注册条款</text>
            </div>
            <text class="button" @click="register">注册</text>
        </div>
    </div>
</template>
<script>
const modal = weex.requireModule("modal");
const navigator = weex.requireModule("navigator");

import mixin from "./mixins/mixin.js";
export default {
    mixins: [mixin],
    methods: {
        // 返回登录界面
        leftback: function(event) {
            navigator.pop({ animated: "true" });
        },
        // 获取验证码
        getiphonecode: function() {
            modal.toast({
                message: "获取手机验证码！"
            });
        },
        // 同意注册条款
        agree: function() {
            modal.toast({
                message: "同意注册条款！"
            });
        },
        // 注册
        register: function() {
            modal.toast({
                message: "注册！"
            });
        }
    }
};
</script>
<style scoped >
.warpper {
    /* background-image: linear-gradient(to bottom, #f35bb6, #7b79f9); */
    background-color: #ffffff;
    flex: 1;
}
.toolbar-warpper {
    /* position: absolute; */
    /* 垂直居中 */
    justify-content: center;
    align-items: center;
    background-color: #309bf8;
    height: 100px;
    /* width: 100px; */
}
.toolbar-leftimage-warpper {
    position: absolute;
    left: 0px;
    top: 0px;
    justify-content: center;
    height: 100px;
}
.toolbar-text {
    font-size: 35px;
    color: #ffffff;
}
.toolbar-leftimage {
    margin-left: 35px;
    width: 35px;
    height: 35px;
}
.input {
    font-size: 35px;
    height: 80px;
    width: 550px;
    padding-left: 60px;
    color: #ffffff;
    padding-top: 35px;
    placeholder-color: #a5a5a5;
    margin-bottom: 35px;
    background-color: rgba(0, 0, 0, 0);
    /* outline: none; */
}
.button {
    font-size: 45px;
    text-align: center;
    padding: 15px;
    margin: 10px;
    border-width: 2px;
    border-style: solid;
    color: #ffffff;
    border-color: #ffffff;
    background-color: #1e90ff;
    border-radius: 10px;
    margin-top: 40px;
}
.code-warpper {
    flex-direction: row;
    align-items: center;
}
.agree-warpper {
    margin-top: 40px;
    margin-left: 50px;
    flex-direction: row;
    /* align-items: center; */
}
.code-text {
    color: #509bd7;
    font-size: 35px;
}
.agree-img {
    margin-top: 3px;
    width: 35px;
    height: 35px;
}
.agree-text {
    color: #509bd7;
    font-size: 35px;
    margin-left: 30px;
}
</style>
