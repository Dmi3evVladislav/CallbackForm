<template>
  <div>
    <div class="bg">
        <section id="up"></section>
        <section id="down"></section>
        <section id="left"></section>
        <section id="right"></section>
    </div>
    
    <div class="content">
        <div class="headtext">
            <h1 class="toptext">Остались вопросы?</h1>
            <h2 class="bottomtext">Ответим на них в кротчайшие сроки</h2>
            <div class="buttondiv">
                <a href="#fb"><button class="askbutton">Спросить</button></a>
            </div>
        </div>
        <div id="fb" class="formbox" @keyup.enter="sendmessage()">
            <div class="form">
                <div class="formact">
                    <div class="topform">
                        <h2>Оставить сообщение</h2>
                        <img src="./img/mailico.png" alt="mail_image">
                    </div>
                    <div class="fsname">
                      <input class="forminput" id="secondname" type="text" placeholder="Фамилия" v-model="secondname" v-on:change="checkchange">
                      <input class="forminput" id="firstname" type="text" placeholder="Имя" v-model="firstname" v-on:change="checkchange">
                    </div>
                    <div class="mobile">
                      <input class="forminput" id="phonenum" type="tel" placeholder="Телефон" v-model="mobilenumber" v-on:change="checkchange">
                    </div>
                    <div class="textarea">
                      <textarea class="formta" id="question" cols="30" rows="5" placeholder="Как мы можем вам помочь?" v-model="message" v-on:change="checkchange"></textarea>
                    </div>
                    <div class="sendbutton">
                      <button class="sendbttn" :disabled="!secondname.length || !firstname.length || !mobilenumber.length || !message.length" v-on:click="sendmessage"><img src="./img/sendicon.png" alt="send_image" ><p>ОТПРАВИТЬ</p></button>
                    </div>
                </div>
            </div>
            <div class="contacts">
                <div class="topcontacts">
                    <h2>Контакты</h2>
                </div>
                <div class="contmobile">
                  <img src="./img/telicon.png" alt="">
                  <p>+7 (987) 654 32 10</p>
                </div>
                <div class="contmail">
                  <img src="./img/mailiconwhite.png" alt="">
                  <p>example@mail.com</p>
                </div>
                <div class="messbuttons">
                  <a href="https://vk.com/vlxdxz"><img src="./img/vkroundicon.png" alt=""></a>
                  <a href="https://t.me/vlxdxz"><img src="./img/tgroundicon.png" alt=""></a>
                </div>
            </div>
        </div>

    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
        firstname: '',
        secondname: '',
        mobilenumber: '',
        message: '',
    }
  },
  methods: {
    sendmessage() {
        console.log(`Firstname: ${this.firstname}, Secondname: ${this.secondname}, PhoneNumber:${this.mobilenumber}, UserMessage: ${this.message}`);
        this.firstname = ''
        this.secondname = ''
        this.mobilenumber = ''
        this.message = ''
    },
  }
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
}
html {
    overflow-y: scroll;
    scroll-behavior: smooth;
}
input {
    -webkit-appearance: none;
    transition: 500ms;
}
html::-webkit-scrollbar {
    width: 3px;
    background-color: rgba(183, 174, 190, 0);
    border-radius: 10px;
    height: 200px;
}

html::-webkit-scrollbar-thumb {
    background: #f5f5f5;
    border-radius: 10px;
}

body {
    margin: 0;
    padding: 0;
    font-family: 'Inter', sans-serif;
    min-height: 100vh;
    background-color: #8E49C3;
    
    animation: bg 16000ms infinite;
}

.bg{
    max-width: 100%;
}
#up {
    z-index: 1;
    position: fixed;
    height: 60vh;
    width: 60vh;
    top: -20%;
    left: 30%;
    border-radius: 50%;
    background-color: #77E268;
    filter: blur(80px);
    animation: up 16000ms infinite;
}
#left {
    z-index: 1;
    position: fixed;
    left: -10%;
    height: 50vh;
    width: 50vh;
    top: 27%;
    border-radius: 50%;
    background-color: #F0A51E;
    filter: blur(80px);
    animation: left 16000ms infinite;
}
#right {
    z-index: 1;
    position: fixed;
    right: 5%;
    height: 50vh;
    width: 50vh;
    top: 45%;
    border-radius: 50%;
    background-color: #A9034C;
    filter: blur(80px);
    animation: right 16000ms infinite;
}

.content {
    z-index: 5;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.headtext {
    padding-top: 5%;
    text-align: center;
    justify-content: center;
    margin-bottom: 25%;
}

.toptext {
    font-size: 4vw;
    margin-bottom: 0.5%;
}

.bottomtext {
    font-size: 2vw;
    margin-bottom: 4vh;
}

.toptext, .bottomtext {
    background: -webkit-linear-gradient(#FFFFFF, #C5C1C1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.askbutton {
    font-size: 25px;
    color: #FFFFFF;
    background-color: transparent;
    border: 3px solid #ffffff;
    border-radius: 8px;
    padding: 15px 35px;
    cursor: pointer;
}

.formbox {
    width: 60%;
    display: flex;
    margin-bottom: 5%;
}
.form{
    width: 70%;
    background-color: #FFFFFF;
    padding: 5vh 2vw 2vw 3vw;
    border-radius: 44px 0 0 44px
}
.topform {
    align-items: center;
    display: flex;
    justify-content: space-between;
    margin-bottom: 6%;
}
.topform > h2 {
    font-size: 1.7vw;
    color: #8F48C1;
}
.topform > img {
    width: 3vw;
}

.contacts {
    padding: 5vh 0 0 2vw;
    width: 30%;
    border-radius: 0px 43px 43px 0px;
    border: 4px solid #FFF;
    background: rgba(217, 217, 217, 0.37);
    background-blend-mode: multiply;
}

.topcontacts {
    align-items: center;
    display: flex;
    margin-bottom: 3vh;
}
.topcontacts > h2 {
    font-size: 1.7vw;
    color: #FFFFFF;
}

.forminput {
    font-size: 1.5vw;
    border: 0;
    border-bottom: 2px solid #D9D9D9;
    padding: 15px 0;
    color: #444444;
    outline: none;
    width: 45%;
}

.fsname {
    width: 100%;
    display: flex;
    justify-content: space-between;
    margin-bottom: 7%;
}
.mobile {
    margin-bottom: 12%;
}
.textarea {
    width: 100%;
    margin-bottom: 5%;
}

.formta {
    width: 100%;
    border: 0;
    border-bottom: 2px solid #D9D9D9;
    outline: none;
    font-size: 1.5vw;
    font-family: 'Inter', sans-serif;
    transition: 500ms;
}

.sendbutton {
    width: 100%;
    display: flex;
    justify-content: flex-end;
}
.sendbttn {
    background-color: #8F48C1;
    color: #FFFFFF;
    border: 0;
    border-radius: 18px;
    padding: 2% 8% 2% 6%;
    font-size: 1.1vw;
    font-weight: bold;
    display: flex;
    align-items: center;
    width: fit-content;
    cursor: pointer;
    transition: 500ms;
}
.sendbttn:disabled {
  background-color: #e1caf1;
  cursor: default;
  transition: 500ms;
}
.sendbttn > p {
    padding-left: 8%;
}

.contmobile, .contmail {
    display: flex;
    color: white;
    align-items: center;
}
.contmobile > img, .contmail > img {
    margin-right: 10px;
    width: 3vw;
}
.contmobile > p, .contmail > p {
    font-size: 1vw;
}
.contmobile {
    margin-bottom: 3vh;
}
.contmail {
    margin-bottom: 5vh;
}
.messbuttons {
    display: flex;
}
.messbuttons > a {
    margin-right: 1vw;
}
.messbuttons > a > img{
    width: 3vw;
}

::placeholder {
    color: #c7c5c5;
}

input:focus {
    border-bottom: 2px solid #8F48C1;
    transition: 500ms;
}
.formta:focus {
    border-bottom: 2px solid #8F48C1;
    transition: 500ms;
}


@keyframes up {
    0% {
        top: -20%;
    }
    33% {
        left: 0;
        background-color: #C34975;
    }
    66% {
        top: 5%;
        left: 60%;
        background-color: #6935f8;
    }
    
}
@keyframes left {
    0% {
        top: 27%;
        left: -10%;
    }
    33% {
        top: 45%;
        right: 20%;
        background-color: #AB563E;
    }
    66% {
        top: 45%;
        left: 45%;
        background-color: #F0A51E;
    }
    
}
@keyframes right {
    0% {
        right: 5%;
        top: 45%;
    }
    33% {
        top: 10%;
        right: 5%;
        background-color: #66BEF7;
    }
    66% {
        top: 20%;
        right: 60%;
        background-color: #77E268;
    }
    
}
@keyframes bg {
    0% {
        background-color: #8E49C3;
    }
    33% {
        background-color: #3C1199;
    }
    66% {
        background-color: #C3498B;
    }
    
}

input:-webkit-autofill,
input:-webkit-autofill:hover, 
input:-webkit-autofill:focus,
input:-webkit-autofill:active  {
     box-shadow: 0 0 0 30px #ffffff inset !important;
}

@media only screen and (max-width: 1200px) {
    .toptext {
        font-size: 5vw;
        margin-bottom: 0.5%;
    }
    .bottomtext {
        font-size: 2.5vw;
        margin-bottom: 4vh;
    }
    .askbutton {
        font-size: 2vw;
        padding: 1.7vh 2.5vw;
    }

    .formbox {
        width: 70%;
    }
    .forminput {
        font-size: 2vw;
        width: 45%;
    }
    .topform > h2 {
        font-size: 2.2vw;
        color: #8F48C1;
    }
    .topform > img {
        width: 4vw;
    }
    .topcontacts > h2 {
        font-size: 2.2vw;
        color: #FFFFFF;
    }
    .formta {
        font-size: 2vw;
    }
    .contmobile > img, .contmail > img {
        width: 4vw;
    }
    .contmobile > p, .contmail > p {
        font-size: 1.2vw;
    }
    .messbuttons > a > img{
        width: 4vw;
    }
    .sendbttn > img {
        width: 3.2vw;
}
}
@media only screen and (max-width: 900px) {
    .toptext {
        font-size: 6vw;
        margin-bottom: 0.5%;
    }
    .bottomtext {
        font-size: 3vw;
        margin-bottom: 4vh;
    }
    .askbutton {
        font-size: 3vw;
        color: #FFFFFF;
        background-color: transparent;
        border: 3px solid #ffffff;
        border-radius: 8px;
        padding: 1.7vh 3.2vw;
        cursor: pointer;
    }

    .formbox {
        width: 80%;
    }
    .forminput {
        font-size: 2.2vw;
        width: 45%;
    }
    .formta {
        font-size: 2.2vw;
    }

    .topform > h2 {
        font-size: 2.4vw;
        color: #8F48C1;
    }
    .topform > img {
        width: 5vw;
    }
    .topcontacts > h2 {
        font-size: 2.4vw;
        color: #FFFFFF;
    }
    .contmobile > img, .contmail > img {
        width: 5vw;
    }
    .contmobile > p, .contmail > p {
        font-size: 1.4vw;
    }
    .messbuttons > a > img{
        width: 5vw;
    }
}
@media only screen and (max-width: 600px) {
    .toptext {
        font-size: 7vw;
        margin-bottom: 0.5%;
    }
    .bottomtext {
        font-size: 3.5vw;
        margin-bottom: 4vh;
    }
    .askbutton {
        font-size: 4vw;
        color: #FFFFFF;
        background-color: transparent;
        border: 3px solid #ffffff;
        border-radius: 8px;
        padding: 1.7vh 3vw;
        cursor: pointer;
    }

    .formbox {
        width: 90%;
        flex-direction: column;
    }
    .form {
        width: initial;
        border-radius: 44px 44px 0 0;
        padding: 5vh 5vw 2vw 5vw;
    }
    .fsname {
        flex-direction: column;
    }
    .forminput {
        font-size: 4vw;
        width: 100%;
    }
    .topform > h2 {
        font-size: 5vw;
        color: #8F48C1;
    }
    .topform > img {
        width: 8vw;
    }
    .formta {
        font-size: 4vw;
    }
    .contacts {
        width: initial;
        padding: 3vh 5vw 4vw 5vw;
        border-radius: 0 0 44px 44px;
    }
    .topcontacts > h2 {
        font-size: 5vw;
        color: #FFFFFF;
    }
    .contmobile > img, .contmail > img {
        width: 10vw;
    }
    .contmobile > p, .contmail > p {
        font-size: 4vw;
    }
    .messbuttons > a > img{
        width: 10vw;
    }

    .sendbttn {
        padding: 1.5vh 6vw 1.5vh 4vw;
        font-size: 4vw;
    }
}
@media only screen and (max-width: 500px) {
    .toptext {
        font-size: 8vw;
        margin-bottom: 0.5%;
    }

    .bottomtext {
        font-size: 4vw;
        margin-bottom: 4vh;
    }
    .askbutton {
        font-size: 4vw;
        color: #FFFFFF;
        background-color: transparent;
        border: 3px solid #ffffff;
        border-radius: 8px;
        padding: 1.7vh 4vw;
        cursor: pointer;
    }
}
</style>
