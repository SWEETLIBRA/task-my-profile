<template>
    <div>
        <form @submit="prevent" action="#" class="form">
            <h3 class="block">Персональная информация</h3>
            <div>
                <label 
                    for="fullName" 
                    class="fullName"
                >
                    <span >Введите ФИО</span>
                </label>
                <input 
                    v-model="fullName"
                    @blur="v$.fullName.$touch" 
                    type="text"
                    id="fuulName"
                    placeholder="Введите ФИО"
                >
                <div 
                    v-if="v$.fullName.$error" 
                    class="inputError"
                >
                    Обязательное поле для ввода*
                </div>
            </div>
            <br>
            <div>
                <label 
                    for="date"
                >
                    <span>Введите дату рождения</span>
                </label>
                <input
                    v-model="contact.birthday"
                    @blur="v$.contact.birthday.$touch"  
                    type="date" 
                    id="date" 
                    placeholder="Введите дату рождения"
                >
                </div>
                <div 
                    v-if="v$.contact.birthday.$error" 
                    class="inputError"
                >
                    Обязательное поле для ввода*
            </div>
            <br>
            <div>
                <label 
                    for="email" 
                    class="email"
                >
                    <span >Введите E-mail</span>
                </label>
                <input 
                    v-model="contact.email" 
                    @blur="v$.contact.email.$touch" 
                    type="email" 
                    id="email" 
                    placeholder="Введите E-mail"
                >
                <div 
                    v-if="v$.contact.email.$error" 
                    class="inputError"
                >
                    Обязательное поле для ввода*<br><span>Должно содержать @ .ru или .com</span>
                </div>
            </div>
            <br>
            <div>
                <label 
                    for="city"
                >
                    <span>Введите город</span>
                </label>
                <input
                    v-model="contact.city"
                    @blur="v$.contact.city.$touch"
                    type="text" 
                    id="city" 
                    placeholder="Введите город"
                >
                <div 
                    v-if="v$.contact.city.$error" 
                    class="inputError"
                >
                    Обязательное поле для ввода*
                </div>
            </div>
        </form>
    </div>
</template>

<script>
import { useVuelidate } from '@vuelidate/core'
import { required, email, minLength } from '@vuelidate/validators'

export default {
   setup:() => 
    ({ v$: useVuelidate() }),
   data() {
        return {
            fullName: '',
            contact: {
                birthday: '',
                email: '',
                city: '',
                number: '',
                language: ''
            }
        }
    },
    validations() {
        return {
            fullName: { required, minLength: minLength(15) },
            contact: {
                birthday: { required },
                email: { required, email },
                city: { required },
                number: { required },
                language: {}
            }
        }
    }
}
</script>

<style scoped>
    .form {
        border: 1px solid rgb(80, 80, 155);
        padding: 20px;
        width: 100%;
        height: 100%;
        text-align: center;
        border-radius: 10px;
        box-sizing: border-box;
    }
    .form label {
        width: 100%;
        display: flex;
        justify-content: space-between;
    }

    .form input {
        border: none;
        box-shadow: 10px 2px 5px rgb(100, 101, 145);
        border-radius: 10px;
    }
    .form input:focus {
        outline: none;
    }
    .inputError {
        color: red;
    }
    .block {
        margin: 0 0 10px;
    }
</style>