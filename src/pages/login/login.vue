<template>
    <mtransition>
        <div class="wrapper">
            <mu-appbar title="登录">
                <mu-icon-button icon="arrow_back" slot="left" @click="back" />
            </mu-appbar>
            <div class="main">
                <ul class="form-list">
                    <li>
                        <mu-text-field v-model="username" label="用户名/手机号" />
                    </li>
                    <li>
                        <mu-text-field v-model="password" label="密码" />
                    </li>
                    <li>
                        <router-link to="/register" tag="a" class="option">注册账号</router-link>
                        <router-link to="" tag="a" class="option">忘记密码</router-link>
                        <mu-raised-button label="登录" primary/>
                    </li>
                </ul>
            </div>
        </div>
    </mtransition>
</template>
<script>
import Mtransition from '@/base/mtransition/mtransition';

export default {
    data() {
        return {
            username: '',
            password: ''
        };
    },
    components: {
        Mtransition
    },
    methods: {
        login() {},
        back() {
            this.$router.back();
        }
    }
};
</script>
<style lang="scss" scoped>
@import '~@/assets/scss/variable.scss';
.wrapper {
    overflow: hidden;
}
.main {
    width: 100%;
    height: 75vh;
    margin-top: 50px;
    .form-list {
        width: 80%;
        margin: 0 auto;
        li {
            padding: 10px 0;
            display: block;
            &:last-child {
                float: right;
                .option {
                    margin-right: 10px;
                    font-size: 14px;
                    color: $color-theme;
                }
                &::after {
                    content: '';
                    clear: both;
                }
            }
        }
    }
}
</style>
