<template>
  <div class="container">
    <div class="row m-2">
      <div class="colomn m-2">
        <h1>SHA-256 Encryptor made in Vue.JS</h1>
        <p>Enter string to encrypt:</p>
        <input type="text" id="message">
        <input class="btn btn-dark" type="button" value="Encrypt!" @click="getEncryptedStr()">
      </div>
      <div class="colomn m-2">
        <textarea id="encrypted" style="width:400px; height:400px;" disabled></textarea>
      </div>
    </div>
  </div>
</template>

<script>
var sha256 = require('js-sha256');

export default {
  name: 'ShaEncryptor',

  methods: {
    getEncryptedStr : function () {
      var encrypted_str = sha256(document.getElementById('message').value);
      document.getElementById('encrypted').value = encrypted_str;
    }
  }
}
</script>

<style scoped>
</style>
