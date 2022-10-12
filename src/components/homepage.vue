<template>
    <!--  -->
    <div class="home">
        <div class="content">
            <div class="header-content">
                <ul class="lang-flag">
                    <li id="lang-vn" @click="changeVn"><img src="../assets/vietnam.png" alt=""></li>
                    <li id="lang-en" @click="changeEn"><img src="../assets/united-states.png" alt=""></li>
                </ul>
            </div>

            <div class="img-content">
                <img src="../assets/275475251_1631055923925887_7002151634470862616_n.jpg" alt="">
                <div class="title" style="text-align: center;">
                    <span>NGUYỄN VIỆT ANH</span>
                    <br />
                    <span>FRONTEND DEVELOPER</span>
                </div>
                <div class="position-mount">
                    <span>{{$t("title.mouse")}}: {{ mouse.x }}, {{ mouse.y }}</span>
                </div>
            </div>

            <div class="footer">
                <span>{{$t("title.idiom")}}</span>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue';
import i18n from './Locales/i18nnn';
import { useMouse } from './mouse';

const mouse = reactive(useMouse());

function changeVn() {
    let langEn: any = document.getElementById('lang-en');
    let langVn: any = document.getElementById('lang-vn');
    i18n.global.locale = 'vn';
    langVn.style.display = 'none';
    langEn.style.transform = 'translate 1s';
    langEn.style.display = 'block';
}

function changeEn() {
    let langEn: any = document.getElementById('lang-en');
    let langVn: any = document.getElementById('lang-vn');
    i18n.global.locale = 'en';
    langVn.style.display = 'block';
    langEn.style.display = 'none';
}
</script>

<style scoped>
#lang-en {
    display: none;
}

.home {
    width: 100%;
    height: 700px;
    display: flex;
    justify-content: center;
    justify-items: center;
    align-items: center;
}

.content {
    display: block;
    width: 370px;
    height: 470px;
    background-color: pink;
    border-radius: 10px;
    padding: 30px;
}

ul {
    padding: 0;
    margin: 0;
}

.lang-flag {
    list-style: none;
    display: flex;
    justify-content: flex-end;
    margin-right: 20px;
}

.lang-flag li {
    cursor: pointer;
}

.img-content {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.img-content img {
    width: 50%;
    border-radius: 50%;
}

.title {
    display: block;
    margin-top: 10px;
}

.title span:first-child {
    display: block;
    color: rgb(84, 185, 185);
}

.title span {
    font-size: 20px;
    font-weight: bold;
}

.position-mount {
    margin-top: 10px;
}

.position-mount span {
    display: block;
    padding: 10px;
    background-color: rgb(172, 174, 228);
    border-radius: 10px;
}

.footer {
    margin-top: 20px;
    text-align: center;
}

.footer span {
    font-size: 20px;
}
</style>