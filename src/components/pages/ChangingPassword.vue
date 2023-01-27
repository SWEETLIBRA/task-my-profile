<template>
    <div>
        <form action="#" class="allPassword">
            <h3 class="block">Изменение пароля</h3>
            <div>
                <label 
                    for="currentPassword"
                >
                    <span >Текущий пароль</span>
                </label>
                <input 
                    v-model="groupPassword.currentPassword" 
                    @blur="v$.groupPassword.currentPassword.$touch" 
                    type="password" 
                    id="currentPassword" 
                    placeholder="Текущий пароль"
                >
            </div>
            <div 
                v-if="v$.groupPassword.currentPassword.$error" 
                class="inputError"
            >
               Введите текущий пароль
            </div>
            <br>
            <div>
                <label 
                    for="newPassword"
                >
                    <span >Новый пароль</span>
                </label>
                <input 
                    v-model="groupPassword.newPassword" 
                    @blur="v$.groupPassword.newPassword.$touch" 
                    type="password" 
                    id="newPassword" 
                    placeholder="Новый пароль"
                >
            </div>
            <div 
                v-if="v$.groupPassword.newPassword.$error" 
                class="inputError"
            >
               Введите новый пароль
            </div>
            <br>
            <div>
                <label 
                    for="confirmPassword"
                >
                    <span >Подтверждение пароля</span>
                </label>
                <input 
                    v-model="groupPassword.confirmPassword" 
                    @blur="v$.groupPassword.confirmPassword.$touch" 
                    type="password" 
                    id="confirmPassword" 
                    placeholder="Подтверждение пароля"
                >
            </div>
            <div 
                v-if="v$.groupPassword.confirmPassword.$error" 
                class="inputError"
            >
               Подтвердите пароль
            </div>
        </form>
    </div>
</template>

<script>
import { useVuelidate } from '@vuelidate/core'
import { required, sameAs, minLength } from '@vuelidate/validators'

export default {
    setup:() => 
    ({ v$: useVuelidate() }),
   data() {
        return {
            groupPassword: {
                currentPassword: '',
                newPassword: '',
                confirmpassword: ''
            }
        }
    },
    validations() {
        return {
            groupPassword: {
                currentPassword: { required, sameAs, minLength: minLength(6) },
                newPassword: { required, sameAs, minLength: minLength(6) },
                confirmPassword: { required, sameAs, minLength: minLength(6) }
            }
        }
    }
}
</script>

<style scoped>
    .allPassword {
        border: 1px solid rgb(80, 80, 155);
        padding: 20px;
        width: 100%;
        height: 100%;
        text-align: center;
        border-radius: 10px;
        box-sizing: border-box;
    }
    .allPassword label {
        width: 100%;
        display: flex;
        justify-content: space-between;
    }

    .allPassword input {
        border: none;
        box-shadow: 10px 2px 5px rgb(100, 101, 145);
        border-radius: 10px;
    }
    .allPassword input:focus {
        outline: none;
    }
    .inputError {
        color: red;
    }
    .block {
        margin: 0 0 10px;
    }
</style>