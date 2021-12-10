<template>
    <div class="row">
      <div class="col-sm-8 m-auto">
          <div class="text-center mb-4">
              <h1>Sign Up</h1>
          </div>
          <form id="login-form" @submit.prevent="handleSubmit">
                <div class="mb-4">
                    <label for="email">Dirección de Correo</label>
                    <input type="email" v-model="state.email" class="form-control form-control-lg" >
                    <span v-if="v$.email.$error"> {{v$.email.$errors[0].$message}} </span>
                </div>
                <div class="mb-4">
                    <label for="nombre">Usuario</label>
                    <input type="text" v-model="state.nombre" class="form-control form-control-lg"  >
                    <span v-if="v$.nombre.$error"> {{v$.nombre.$errors[0].$message}} </span>
                </div>
                <div class="mb-4">
                    <label for="password">Contraseña </label>
                    <input type="password" v-model="state.password.password" class="form-control form-control-lg" > 
                    <span v-if="v$.password.password.$error"> {{v$.password.password.$errors[0].$message}}</span>
                </div>
                <div class="mb-4">
                    <label for="passwordConfirm">Confirmar Contraseña </label>
                    <input type="password" v-model="state.password.repeatPassword" class="form-control form-control-lg" onpaste="return false;" > 
                    <span v-if="v$.password.repeatPassword.$error">  {{v$.password.repeatPassword.$errors[0].$message}} </span>
                </div>
                <div class="mb-4">
                    <button @click="submitForm" class="btn btn-primary btn-lg col-sm-6">Sign Up</button>
                </div>
            </form>
            <div class="mb-4">
                <p>Ya estás registrado? <router-link to="/login"> Login </router-link></p>
            </div>
      </div>
  </div>

</template>

<script>

import useValidate from '@vuelidate/core'
import { required, sameAs, minLength, email} from '@vuelidate/validators'
import { computed, reactive } from '@vue/reactivity'

export default {
    setup() {
        const state = reactive({
            nombre: '',
            email: '',
            password: {
                password: '',
                repeatPassword: '',
            },
        })

        const rules = computed(() => {
            return {
                nombre: {required},
                email: {required, email},
                password: {
                    password: {required, minLength: minLength(8)},
                    repeatPassword: {required, sameAs: sameAs(state.password.password)} ,
                },
            };
        });

        const v$ = useValidate(rules, state)

        return{
            state,
            v$
        }
    },
    methods: {
        submitForm() {
            this.v$.$validate()
            if(!this.v$.$error){
                alert('enviado')
            }else{
                alert('revisar los campos')
            }
            // console.log(this.v$)
        },
    },
}
</script>

<style>

</style>