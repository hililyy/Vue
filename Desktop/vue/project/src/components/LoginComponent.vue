<template>
    <div class ="login">
        <img id = "instagram" src="../assets/instagram.png">
        <input type = "text" v-model ="id" placeholder="전화번호, 사용자 이름 또는 이메일"> <br>
        <input type = "password" v-model ="password" placeholder="비밀번호"> <br>
        <router-link to= "/login" ><button @click="login">로그인</button><br></router-link>
        <!-- <h1>{{또는}}</h1> -->
        <br>
            <div id ="test">
                <img id="icon" src="../assets/facebook.png">
                <a id ="facebook" href = "#">Facebook으로 로그인</a>
            </div>
        <br>
            <div id ="searchPassword"> 
                <a id = "search" href = "#">비밀번호를 잊으셨나요?</a>
            </div>
    </div>
</template>
<script>
    export default {
        methods: {
            login(){
                if(this.id != "" && this.password != ""){
                    // var value1 = this.id && this.id.trim();
                    // var value2 = this.password && this.password.trim();
                    console.log(this.id);
                    console.log(this.password);
                    localStorage.setItem(this.id, this.id);
                    localStorage.setItem(this.password, this.password);
                }

            }
        }
    }
</script>


<style scoped>
    .login {
        text-decoration: none;
    }
    #search {
        text-decoration: none;
    }
    
    #test {
        text-align : center;
    }
    
    #searchPassword {
        text-decoration: none;
        font-size :15px;
        text-align : center;
        
    }
    #facebook {
        text-decoration: none;
        font-size :20px;   
       
    }
    #instagram {
        width : 100%;
        height : 150px;
        object-fit :contain;
        display: block;
        margin-left: auto;
        margin-right: auto;
    }
    #icon {
        width : 20px;
        height : 20px;
        margin-right: 7px;
    }
    input { 
        background : rgb(238, 237, 237);
        width : 90%;
        height : 50px;
        /* margin-bottom : 10px; */
        border-style : solid;
        border-radius : 0.5em;
        border-width : 1px 1px 1px 1px;
        border-color : rgb(201, 201, 201);
        font-size : 1rem;
        padding-left: 20px;
        display: block;
        margin-left: auto;
        margin-right: auto;
    }
    button {
        background :rgb(183, 206, 245);
        width : 95%;
        height : 40px;
        border-style : none;
        border-radius : 0.5em;
        color : white;
        font-size : 1.1rem;
        /* margin-top : 10px; */
        font-weight : bold;
        display: block;
        margin-left: auto;
        margin-right: auto;
    }


</style>