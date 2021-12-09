<template>
  <div class="row">
      <div class="col-sm-8 m-auto">
          <div class="text-center mb-4">
              <h1>Log In</h1>
          </div>
          <form id="login-form">
                <div class="mb-4">
                    <label for="email">Dirección de Correo</label>
                    <input type="email" class="form-control form-control-lg" required >
                </div>
                <div class="mb-4">
                    <label for="password">Contraseña </label>
                    <input type="password" class="form-control form-control-lg" minlength="8" maxlength="16" required pattern="^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?!.*\s).*$" title="La contraseña debe contener Mayúsculas, Minúsculas, Números y un Mínimo de 8 Caracteres"> 
                </div>
                <div class="mb-4">
                    <button class="btn btn-primary btn-lg col-sm-6">Login</button>
                </div>
            </form>
            <div class="mb-4">
                <p> <router-link to="/reset"> Olvidaste tu contraseña?</router-link></p>
            </div>
            <div class="mb-4">
                <p>Aún no estás registrado? <router-link to="/signup"> Sign Up </router-link></p>
            </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>