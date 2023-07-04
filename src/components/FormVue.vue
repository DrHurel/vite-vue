<script setup lang="ts">

  import {ref} from 'vue'

  const isValid = ref(false)
  const email = ref('')

  function submitForm() {
    console.log('submitForm')
    console.log(email.value)
    isValid.value = true
    return 0
  }

  function reset() {
    isValid.value = false
    return 0
  }


</script>

<template>

  <section v-if="isValid" class="confirmationMessage">
    <img src="../assets/images/icon-success.svg" alt="">

    <h1>Thanks for subscribing!</h1>
    <p>
      A confirmation email has been sent to
    <strong>ash@loremcompany.com</strong>
    
      . Please open it and click the button inside to confirm
    your subscription. 
    </p>
    <button @click="reset">
      Dismiss message
    </button>

    <!-- Success message end -->
  </section>

  <section v-else="isValid"  class="formContainer">
    <div>
      <h1>Stay updated!</h1>
      <p>Join 60,000+ product managers receiving monthly updates on:</p>
      <ul>
        <li>Product discovery and building what matters</li>
        <li>Measuring to ensure updates are a success</li>
        <li>And much more!</li>
      </ul>
      
    </div>

    <form  @submit.prevent="submitForm">

      <label for="email-input">
        Email address
      </label>
      <input 
        type="email"
        name="email"
        
        v-model="email"
        placeholder="email@company.com"
        required
        id="email-input"
      />
      <button type="submit">Subscribe to monthly newsletter</button>
    </form>
    <img src="../assets/images/illustration-sign-up-desktop.svg" alt="">
  
  </section>

</template>
