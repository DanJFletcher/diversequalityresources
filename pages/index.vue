<template>
  <div>
    <h1>Hey</h1>
    <form id="my-form" name="contact" method="POST" netlify>
      <input type="hidden" name="form-name" value="contact" />
      <p>
        <label>Your Name: <input type="text" name="name" /></label>
      </p>
      <p>
        <label>Your Email: <input type="email" name="email" /></label>
      </p>
      <p>
        <label>Message: <textarea name="message"></textarea></label>
      </p>
      <p>
        <button type="submit" @click="submit">Send</button>
      </p>
    </form>
  </div>

</template>

<script>

import $ from 'jquery'

export default {
  methods: {
    submit (e) {
      e.preventDefault()

      var $form = $(this)
      $.post($form.attr('action'), $form.serialize()).then(function () {
        alert('Thank you!')
      })
    }
  }
}
</script>
