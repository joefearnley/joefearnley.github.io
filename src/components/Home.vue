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
            <li><a @click="email()" href="#" class="icon fa-envelope"><span class="label">Email</span></a></li>
          </ul>
        </nav>
    </header>
  </div>
  <div class="modal" v-bind:class="{ 'is-active': showEmailForm }">
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
              <input class="input" type="text" name="subject" placeholder="Subject">
            </div>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea" name="body" placeholder="Hi Joe, ..."></textarea>
            </div>
          </div>
        </form>
      </section>
      <footer class="modal-card-foot">
        <button class="button is-success">
          <span class="icon is-small">
            <i class="fas fa-envelope"></i>
          </span>
          Send
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
      showEmailForm: false
    }
  },
  methods: {
    email: function() {
      this.showEmailForm = true;
    },
    hideEmailForm: function() {
      this.showEmailForm = false;
    }
  }
}
</script>
