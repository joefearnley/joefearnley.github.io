<template>
<div id="wrapper">
  <div id="main">
    <header id="header">
        <h1>Joe Fearnley</h1>
        <p>Developer &nbsp;&bull;&nbsp; Pizza Eater &nbsp;&bull;&nbsp; Some Music</p>
        <nav>
          <ul>
            <li><a href="https://github.com/joefearnley" class="icon fa-github"><span class="label">Github</span></a></li>
            <li><a href="https://twitter.com/joefearnley" class="icon fa-twitter"><span class="label">Twitter</span></a></li>
            <li><a href="https://instagram.com/joefearnley" class="icon fa-instagram"><span class="label">Instagram</span></a></li>
            <li><a href="https://www.linkedin.com/in/joefearnley" class="icon fa-linkedin"><span class="label">LinkedIn</span></a></li>
            <li><a @click="showEmailForm()" href="#" class="icon fa-envelope"><span class="label">Email</span></a></li>
          </ul>
        </nav>
    </header>
  </div>
  <div class="modal" v-bind:class="{ 'is-active': showEmailFormModal }">
    <div class="modal-background"></div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title">Email Joe</p>
        <button @click="hideEmailForm" class="delete" aria-label="close"></button>
      </header>
      <section class="modal-card-body">
        <form>
          <div class="field">
            <div class="control">
              <input class="input" v-bind:class="{ 'is-danger': nameInvalid }" @change="validateField('name')" type="text" name="name" v-model="fields.name" placeholder="Name">
            </div>
            <p v-show="nameInvalid" class="help is-danger">Name is required</p>
          </div>
          <div class="field">
            <div class="control">
              <input class="input" v-bind:class="{ 'is-danger': emailInvalid }" @change="validateField('email')" type="text" name="email" v-model="fields.email" placeholder="Email">
            </div>
            <p v-show="emailInvalid" class="help is-danger">Email is required</p>
          </div>
          <div class="field">
            <div class="control">
              <input class="input" v-bind:class="{ 'is-danger': subjectInvalid }" @change="validateField('subject')" type="text" name="subject" v-model="fields.subject" placeholder="Subject">
            </div>
            <p v-show="subjectInvalid" class="help is-danger">Subject is required</p>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea" v-bind:class="{ 'is-danger': bodyInvalid }" @change="validateField('body')" name="body" v-model="fields.body" placeholder="Hi Joe, ..."></textarea>
            </div>
            <p v-show="bodyInvalid" class="help is-danger">Body is required</p>
          </div>
        </form>
      </section>
      <footer class="modal-card-foot">
        <button @click="sendEmail" class="button is-success has-background-grey">
          <span class="icon is-small">
            <i class="fa fa-envelope"></i>
          </span>
         <span>Send</span>
        </button>
        <button @click="hideEmailForm" class="button">Cancel</button>
      </footer>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      fields: {
        name: '',
        email: '',
        subject: '',
        body: ''
      },
      showEmailFormModal: false,
      nameInvalid: false,
      emailInvalid: false,
      subjectInvalid: false,
      bodyInvalid: false
    }
  },
  methods: {
    showEmailForm: function() {
      this.showEmailFormModal = true;
    },
    hideEmailForm: function() {
      this.showEmailFormModal = false;
    },
    sendEmail: function() {
      if (!this.validateForm()) {
        return false;
      }
    },
    validateForm: function() {
      Object.keys(this.fields).forEach(key => {
        this[key + 'Invalid'] = false;
        if (this.fields[key] === '') {
          this[key + 'Invalid'] = true;
        }
      });
    },
    validateField: function(key) {
      if (this.fields[key] !== '') {
        this[key + 'Invalid'] = false;
      }
    }
  }
}
</script>

<style>
a {
  color: #4a4a4a;
}
</style>
