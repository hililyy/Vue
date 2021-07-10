<template>
    <div class ="menu">
        <img id = "instagram" src="../assets/instagram.png">
        <input id ="search" type="text" v-model="search"  placeholder="검색"> 
            <img id ="home" src="../assets/home.png">
            <img id ="send" src="../assets/send.png">
            <img id = "compass" src="../assets/compass.png">
            <img id ="heart" src="../assets/heart.png">

    </div>
</template>

<script>

</script>


<style>
    .menu {
        text-align : center;
    }
 
    #home {
        width : 30px;
        height : 30px;
        object-fit :contain;
        margin : 0px 10px 0px 50px;
        padding-bottom : 10px;
    }
    #compass {
        width : 30px;
        height : 30px;
        object-fit :contain;
        margin : 0px 10px 0px 10px;
        padding-bottom : 10px;
    }
    #send {
        width : 30px;
        height : 30px;
        object-fit :contain;
        margin : 0px 10px 0px 10px;
        padding-bottom : 10px;
    }
    #heart {
        width : 30px;
        height : 30px;
        object-fit :contain;
        margin : 0px 10px 0px 10px;
        padding-bottom : 10px;
    }
    #instagram {
        width : 100px;
        height : 50px;
        object-fit :contain;
        margin-right : 50px;
    }

</style>