
<template>
  <div class="contacterNousSection mt-2 py-2">
    <h1 class="text-center text-orange mt-5 fs-1">Contacter Nous</h1>

    <div class="formContent mx-auto px-3 py-2">
      <form class="my-2">
        <div class="mb-3">
          <input
            v-model="v$.contactForm.email.$model"
            class="productElement w-100 p-2"
            type="email"
            placeholder="Votre Email"
          />
          <small
            v-if="v$.contactForm.email.$error"
            class="text-red float-start py-2 px-3"
          >
            {{ v$.contactForm.email.$errors[0].$message }}
        </small>
        </div>

        <div class="row w-100 m-0">
          <div class="col-md-6 mb-3 p-0">
            <input
              v-model="v$.contactForm.lastName.$model"
              class="productElement w-100 p-2"
              type="text"
              placeholder="Votre nom"
            />
            <small
              v-if="v$.contactForm.lastName.$error"
              class="text-red float-start py-2 px-3"
            >
              {{ v$.contactForm.lastName.$errors[0].$message }}
          </small>
          </div>
          <div class="col-md-6 mb-3 p-0 ">
            <input
              v-model="v$.contactForm.firstName.$model"
              class="productElement w-100 p-2"
              type="text"
              placeholder="Votre prenom"
            />
            <small
              v-if="v$.contactForm.firstName.$error"
              class="text-red float-start py-2 px-3"
            >
              {{ v$.contactForm.firstName.$errors[0].$message }}
          </small>
          </div>
        </div>
        
        <div class="mb-3">
          <div class="productElement">
            <textarea
              v-model="v$.contactForm.message.$model"
              class="w-100 h-100 p-2 textAreaStyling text-white"
              label="votre message"
              rows="3"
            ></textarea>
          </div>
          <small
            v-if="v$.contactForm.message.$error"
            class="text-red float-start py-2 px-3"
          >
            {{ v$.contactForm.message.$errors[0].$message }}
          </small>
        </div>

          <div class="">
            <button class="btn btn-orange text-white fs-5 w-100" type="button" @click="sendMessage">Envoyer</button>
          </div>
      </form>

      <div class="d-flex justify-content-between flex-wrap text-white flexDirection">
        <div class="d-none d-lg-inline-flex">
          <img src="@/assets/parisCity.webp" class="img-fluid" alt="" height="300" width="300" />
        </div>
        
        <div class="text-start mt-5">
          <h3>Adresse</h3>
          <p>
            Medicusstrasse 5<br>
            Paris, 75008 <br>
            France<br>
          </p>
        </div>

        <div class="text-start mt-5">
          <h3>Contact</h3>
          <p>
            <strong class="text-orange">Phone:</strong> +33 6 41 27 38 32<br>
            <strong class="text-orange">Phone:</strong> +33 6 64 27 86 57<br>
            <strong class="text-orange">Email:</strong> contact@ubibat.fr<br>
            <strong class="text-orange">Email:</strong> etude@ubibat.fr<br>
          </p>
        </div>
      </div>
    </div>
  </div>
    
</template>

<script>

import { useVuelidate } from '@vuelidate/core'
import { required, email } from '@vuelidate/validators'
import Swal from 'sweetalert2'
import emailjs from '@emailjs/browser'

export default {
  setup() {
    return { v$: useVuelidate() }
  },

  data() {
    return {
      contactForm: {
        email: null,
        gender: null,
        firstName: null,
        lastName: null,
        message: null,
      },
    }
  },

  methods: {
    
    async sendMessage() {
      const templateParams = {
        first_name: this.contactForm.firstName,
        last_name: this.contactForm.lastName,
        from_email: this.contactForm.email,
        message: this.contactForm.message,
      }
      this.v$.$validate()
      if (this.v$.$error) {
        Swal.fire({
          icon: 'error',
          title: 'Oops',
          text: 'Un problème est survenu. Veuillez réessayer de nouveau',
          confirmButtonText: 'Okey',
        })
        return
      } else {
        emailjs.send(
          process.env.VUE_APP_EMAILJS_SERVICE_ID,
          process.env.VUE_APP_EMAILJS_TEMPLATE_ID,
          templateParams,
          process.env.VUE_APP_EMAILJS_PUBLIC_KEY,
        ).then(() => {
          this.contactForm.message = null
          this.v$.$reset()
          Swal.fire({
            icon: 'success',
            title: 'Message envoyer',
            text: 'Merci pour votre message. Nous vous répondrons dans les plus brefs délais.',
            confirmButtonText: 'Okey',
          });
        })
        .catch(() => {
          Swal.fire({
          icon: 'error',
          title: 'Oops',
          text: 'Un problème est survenu. Veuillez réessayer de nouveau',
          confirmButtonText: 'Okey',
          })
        })
      }
    },
    
  },
  validations() {
    return {
      contactForm: {
        firstName: { required },
        lastName: { required },
        email: { required, email },
        message: { required },
      },
    }
  },
}
</script>

<style scoped lang="scss">
.flexDirection{
  flex-direction: column;
}
.contacterNousSection{
  background-color: #031136;
  background-size: cover;
}
.formContent{
  width: 100%;
  .productElement {
    font-family: 'Alegreya', serif;
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
    box-shadow: 0 25px 45px rgba(0, 0, 0, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.5);
    border-top: 1px solid rgba(255, 255, 255, 0.75);
    border-left: 1px solid rgba(255, 255, 255, 0.75);
    border-radius: 20px;
    color: #fff;
    &:focus{
      outline: none;
      border: none !important;
    }
    &::placeholder {
      color: #fff;
    }
  }
  .textAreaStyling{
    background: transparent;
    border: none;
    &:focus {
      outline: none;
    }
  }
  .btn-orange{
    background-color: var(--main-orange-color);
    &:hover{
      background-color: var(--main-orange-color);
    }
  }
}

@media (min-width: 992px) {
  .flexDirection{
    flex-direction: row;
  }
  .formContent{
    width: 60%;
  }
}
</style>
