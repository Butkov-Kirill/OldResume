<script>

import {Email} from '../../smtp.js';

export default{
    data(){
        MessageSend : false
    },
    methods:{
        GoogleBotton(){
            var bufer = document.createElement('textarea');
            bufer.value = "programmer.man.2018@gmail.com";
            document.body.appendChild(bufer);
            bufer.select();
            document.execCommand('copy');
            document.body.removeChild(bufer);
            alert("Почта programmer.man.2018@gmail.com скопирована в буфер обмена!");
        },
        SendMessage(){
            let user_name = this.$refs.name_input.value;
            let user_email = this.$refs.email_input.value;
            let user_message = this.$refs.message_box.value;
            
            if (user_name && user_email && user_message && !this.MessageSend){
                Email.send({
                    Host: "smtp.gmail.com",
                    Username: "kbutkovresume@gmail.com",
                    Password: "$#%grereh3t523gddg$#",
                    To: "programmer.man.2018@gmail.com",
                    From: "kbutkovresume@gmail.com",
                    Subject: "Message from site",
                    Body: "Name: "+user_name+".<br>Email: "+user_email+"<br>Message: "+user_message,
                }).then(message => this.SendSignal());
            } else if(!this.MessageSend) {
                var signalText = this.$refs.permision;
                signalText.style.color = "rgb(218, 40, 40)";
                signalText.innerText = "Необходимо заполнить все поля!";
                signalText.style.opacity = "1";
            } else if (this.MessageSend){
                var signalText = this.$refs.permision;
                signalText.style.color = "rgb(218, 40, 40)";
                signalText.innerText = "Вы уже отправили письмо!";
                signalText.style.opacity = "1";
            }
        },
        SendSignal(){
            var signalText = this.$refs.permision;
            signalText.style.color = "green";
            signalText.innerText = "Письмо успешно отправлено, ожидайте ответа!";
            signalText.style.opacity = "1";
            this.MessageSend = true;
        },
    }
}
</script>

<template lang="pug">
.Contacts
    .sides
        .left
            .Person
                img.avatar(src="../../assets/images/src/ava.png")
                .name-person Бутков Кирилл Александрович
            .Buttons
                a(href="https://www.instagram.com/invites/contact/?i=1l2rpcwj66hzd&utm_content=mkixo7g").button
                    i(class="fab fa-instagram fa-lg")
                    p Instagram
                a(href="https://t.me/SALVADOR_BEATS").button
                    i(class="fab fa-telegram fa-lg")
                    p Telegram
                a(href="https://vk.com/salvador.salvador").button
                    i(class="fab fa-vk fa-lg")
                    p VK
                a(@mousedown = "GoogleBotton").button
                    i(class="fab fa-google fa-lgl")
                    p Gmail
        .right
            h1 ОТПРАВИТЬ ПИСЬМО
            p.permission(ref="permision") Вам необходимо заполнить все поля!
            .form(method="POST", action = "send_email.php", ref="form_send_message")
                input(type="name", ref="name_input", placeholder="Name", name="user_name")
                input(type="email", ref="email_input", placeholder="Email", name="user_email")
                textarea(ref="message_box", placeholder="Your message", name="user_message")
                button(v-on:click = "SendMessage()", ref="button_send_message") send message
</template>

<style lang="scss">
.Contacts{
    .sides{
        display: flex;
        width: 100%;
        margin: 0 auto;
        padding: 37px 37px 0 37px;
        .left{
            width: 50%;
            .Person{
                display: flex;
                img{
                    width: 120px;
                    height: 120px;
                    box-shadow: 2px 2px 20px rgba(0, 0, 0, 0.233);
                    image-rendering: optimizeSpeed;
                }
                .name-person{
                    margin-left: 15px;
                    font-family: 'Montserrat Light', sans-serif;
                    font-style: normal;
                    font-weight: 100;
                    font-size: 24px;
                    line-height: 35px;
                    letter-spacing: 0.15em;
                }
            }
            .Buttons{
                margin-top: 37px;
                .button{
                    display: flex;
                    width: 50%;
                    background: rgba(255, 255, 255, 0.514);
                    padding: 10px 22px 10px 22px;
                    margin-bottom: 40px;
                    border-radius: 25px;
                    font-family: 'Montserrat Light', sans-serif;
                    font-weight: 100;
                    font-size: 20px;
                    text-decoration: none;
                    color: #000;
                    box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.144);
                    cursor: pointer;

                    &:hover{
                        background: rgb(255, 255, 255);
                        box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.247);
                        transition: 0.5s;
                    }

                    i{
                        margin: 0;
                    }
                    p{
                        margin: 0;
                        margin-left: 10px;
                    }
                }
            }
        }
        .right{
            width: 50%;
            h1{
                font-family: 'Montserrat Light', sans-serif;
                font-weight: 100;
                font-size: 36px;
                line-height: 35px;
                text-align: center;
            }
            .permission{
                text-align: center;
                color: rgb(218, 40, 40);
                opacity: 0;
                font-family: 'Montserrat Light', sans-serif;
                font-weight: 100;
            }
            .form{
                width: 75%;
                margin: 0 auto;
                display: flex;
                flex-direction: column;

                input{
                    padding: 10px 20px 10px 20px;
                    font-weight: 200;
                    font-family: 'Montserrat Light', sans-serif;
                    font-size: 18px;
                    background: rgba(255, 255, 255, 0.466);
                    border: none;
                    border-bottom: 2px solid #000;
                    margin-bottom: 20px;
                    box-shadow: 2px 2px 15px rgba(0, 0, 0, 0.158);
                }

                textarea{
                    padding: 10px 20px 10px 20px;
                    font-weight: 200;
                    font-family: 'Montserrat Light', sans-serif;
                    font-size: 18px;
                    background: rgba(255, 255, 255, 0.466);
                    border: none;
                    border-bottom: 2px solid #000;
                    margin-bottom: 20px;
                    box-shadow: 2px 2px 15px rgba(0, 0, 0, 0.158);
                    height: 150px;
                    resize: none;
                }

                button{
                    border: none;
                    background: #3E3E3E;
                    border-radius: 25px;
                    width: auto;
                    color: #fff;
                    padding: 15px 10px 15px 10px;
                    font-family: 'Montserrat Light', sans-serif;
                    font-weight: 100;
                    font-size: 18px;
                    text-transform: uppercase;
                    letter-spacing: 0.15em;
                    width: 70%;
                    box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.144);

                    &:hover{
                        background: #242424;
                        box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.37);
                        transition: 0.5s;
                    }
                }

                input:focus{
                    outline: none;
                }

                textarea:focus{
                    outline: none;
                }
            }
        }
    }
}

@media (max-width: 800px) {
.Contacts{
    .sides{
        display: flex;
        flex-direction: column;
        margin: 0;
        padding: 0;
        .left{
            width: 100%;
            margin-left: 20px;
            margin-top: 20px;
            .Person{
                .name-person{
                    font-size: 18px;
                    line-height: 30px;
                }
            }
            .Buttons{
                margin-top: 25px;
                .button{
                    margin-bottom: 25px;
                }
            }
        }
        .right{
            width: 100%;
            margin-top: 30px;
            h1{
                font-size: 30px;
            }
            form{
                width: 80%;

                input{
                    font-size: 16px;
                }

                textarea{
                    font-size: 16px;
                }
            }
        }
    }
}
}
</style>