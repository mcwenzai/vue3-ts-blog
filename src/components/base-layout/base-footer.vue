<template>
    <footer class="base-footer__wrapper">
        <div class="base-footer__inner">
            <section class="footer-column">
                <h3>关于本站</h3>
                <p>
                    文仔博客，专注于前端技术分享。除特殊说明外，本站内文章均为博主原创，转载前请联系博主授权，授权后方可转载！转载时，请在显眼位置注明原文出处，谢谢合作！
                </p>
            </section>
            <section class="footer-column">
                <h3>公众号&小程序</h3>
                <div class="wechat-qrcodes">
                    <el-image
                        :src="publicAccoutQrcode"
                        title="公众号-大前端技术沙龙"
                        class="qrcode"
                        lazy
                        :preview-src-list="[publicAccoutQrcode, mpQrcode]"
                    />
                    <el-image
                        :src="mpQrcode"
                        title="小程序-文仔博客"
                        class="qrcode"
                        lazy
                        :preview-src-list="[publicAccoutQrcode, mpQrcode]"
                    />
                </div>
            </section>
            <section class="footer-column">
                <h3>联系&交流</h3>
                <ul class="social-list">
                    <li>
                        <icon-svg title="微信号" icon="wechat" />
                        <a
                            target="_blank"
                            href="https://qncdn.wbjiang.cn/%E5%BE%AE%E4%BF%A1%E4%BA%8C%E7%BB%B4%E7%A0%81%E5%90%8D%E7%89%87.jpg"
                            >laobaife</a
                        >
                    </li>
                    <li>
                        <icon-svg title="我的邮箱" icon="email" />
                        <span>cumtrobin@163.com</span>
                    </li>
                    <li>
                        <icon-svg title="github" icon="github" />
                        <a target="_blank" href="https://github.com/mcwenzai">https://github.com/mcwenzai</a>
                    </li>
                </ul>
            </section>
            <section class="footer-column">
                <h3>友情推荐</h3>
                <a-row :gutter="12">
                    <a-col :span="12">
                        <a target="_blank" href="http://www.wbjiang.cn">Tusi个人主页</a>
                    </a-col>
                    <a-col :span="12">
                        <a target="_blank" href="http://hexo.wbjiang.cn">文仔博客(Hexo版)</a>
                    </a-col>
                    <a-col :span="12">
                        <a target="_blank" href="https://juejin.im/user/5ca40a18f265da30b8178b31/posts">Tusi的掘金</a>
                    </a-col>
                    <a-col :span="12">
                        <a target="_blank" href="https://blog.csdn.net/weixin_41196185">Tusi的CSDN</a>
                    </a-col>
                    <a-col :span="12">
                        <a target="_blank" href="https://www.whatled.com/">少将全栈</a>
                    </a-col>
                </a-row>
            </section>
        </div>
    </footer>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    name: "BaseFooter",
    setup() {
        return {
            publicAccoutQrcode: "https://qncdn.wbjiang.cn/qrcode.jpg",
            mpQrcode: "https://qncdn.wbjiang.cn/Tusi%E5%8D%9A%E5%AE%A2.jpg",
        };
    },
});
</script>

<style lang="scss" scoped>
.base-footer__wrapper {
    background-color: #121212;
    color: #ceb8bb;
    padding: 18px 24px;
    .footer-column {
        position: relative;
        + .footer-column {
            margin-top: 24px;
            &::after {
                content: "";
                position: absolute;
                top: -10px;
                left: 0;
                width: 100%;
                height: 1px;
                background-color: #ccc;
            }
        }
        > h3 {
            margin: 10px 0;
            font-size: 18px;
            color: #efefef;
            font-weight: 700;
        }
        > p {
            margin: 6px 0;
            font-size: 12px;
        }
        a {
            font-size: 16px;
            line-height: 1.8;
        }
    }

    .social-list {
        li + li {
            margin-top: 6px;
        }

        .icon-svg,
        span,
        a {
            vertical-align: middle;
            font-size: 16px;
        }

        .icon-svg {
            margin-right: 10px;
            font-size: 24px;
            color: #a8c0cc;
        }
    }
}

.wechat-qrcodes {
    display: flex;
}

:deep(.qrcode) {
    flex: 1;
    max-width: 200px;
    + .qrcode {
        margin-left: 10px;
    }
}

@media screen and (min-width: 992px) {
    .base-footer__inner {
        width: 800px;
        margin: 0 auto;
    }
}
</style>
