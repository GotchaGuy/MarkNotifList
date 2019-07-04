
<template>
    <section>
            <div class="notification" v-bind:class="{'seen':notif.seen}" v-for="(notif, index) in info" v-bind:key="index" >

                <div>
                    <img :src="notif.icon" alt="icon">
                </div>
                <div class="text">
                    <p >{{notif.message}}</p>
                </div>
            </div>
        </section>
</template>

   <script>
export default {
    name: "Notifications",
        props: {
        info: Array
    },


}
</script>

<style lang="scss">
       
        div.notification {
            width: 560px;
            height: 80px;
            color: rgb(37, 46, 54);
            background-color: rgb(82, 82, 82);
            box-shadow: 1px solid black;
            margin-bottom: 10px;
            margin: 0 auto 10px auto;
            
            div {
                height: 80px;
                width: 80px;
                float: left;
                img {
                    height: 100%;
                    width: auto;
                }
            }
            div.text {
                    height: 80px;
                    width: 480px;
                    float: left;
                p {
                    height: 30px;
                    font-size: 16px;
                    line-height: 30px;
                    text-align: left;
                    color: rgb(0, 0, 0);
                    background-color: rgb(255, 184, 51);
                }

            }
        }
        .seen {
            opacity: 0.5;
        }
    </style>

 