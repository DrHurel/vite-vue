<script setup lang="ts">

  import {ref} from 'vue'

  const isValid = ref(false)

  function submitForm() {
    isValid.value = true
    return 0
  }

  function reset() {
    isValid.value = false
    return 0
  }


</script>

<template>
  <section v-if="isValid">
    <!-- Success message start -->
    <h1>Thanks for subscribing!</h1>
    <p>
      A confirmation email has been sent to
    ash@loremcompany.com. Please open it and click the button inside to confirm
    your subscription. 
    </p>
    <button @click="reset">
      Dismiss message
    </button>

    <!-- Success message end -->
  </section>

  <section v-else="isValid">
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
        placeholder="email@company.com"
        required
        id="email-input"
      />
      <button type="submit">Subscribe to monthly newsletter</button>
    </form>

    

    <div class="attribution">
      Challenge by
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
        >Frontend Mentor</a
      >. Coded by <a href="#">Your Name Here</a>.
    </div>
  </section>
</template>
