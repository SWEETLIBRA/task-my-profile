<template>
    <div class="blockAvatar">
        <h3 class="block">Изменение аватара</h3>
        <img class="avatar" :src="require('../../../public/assets/User-Profile-PNG-High-Quality-Image.png')" />
        <div class="changeAvatar"> 
            <!-- <button type="submit" class="chaning-avatar">Изменить аватар</button> -->
            <label for="avatar"><span>Изменить аватар</span></label>
            <input type="file" id="avatar">
            
            <br>
            <button type="submit">Удалить аватар</button>
        </div>
    </div>
</template>

<script>

export default {

}
</script>

<style scoped>
.blockAvatar {
    width: 100%;
    text-align: center;
    border: 1px solid rgb(80, 80, 155);
    padding: 20px;
    border-radius: 10px;
    box-sizing: border-box;
    padding-top: 20px;
}

 .avatar {
    width: 70px;
    height: 70px;
 }

 .changeAvatar button {
    border: none;
    border-radius: 10px;
    background: rgb(100, 101, 145);
    color: white;

 }

 .blockAvatar label {
        width: 100%;
        display: flex;
        justify-content: space-between;
    }

    .blockAvatar input {
        border: none;
        box-shadow: 10px 2px 5px rgb(100, 101, 145);
        margin-bottom: 10px;
    }

    .block {
        margin: 0;
    }
</style>