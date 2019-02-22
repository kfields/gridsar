<template>
  <Layout>
    <div class="section">
      <h1>Contact</h1>
    <form name="contact" method="POST" @submit.prevent="handleSubmit">
      <q-input name="subject" v-model="subject" label="Subject"></q-input>

      <q-input name="name" type="name" v-model="name" label="Name"></q-input>
      <q-input name="email" type="email" v-model="email" label="Email"></q-input>

      <q-input name="message" v-model="message" type="textarea" label="Message"></q-input>

      <p class="q-pt-md">
        <q-btn type="submit">
          Send message
        </q-btn>
      </p>
    </form>
    </div>
  </Layout>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      subject: '',
      name: '',
      email: '',
      message: ''
    }
  },
  mounted () {
  },
  methods: {
    handleSubmit () {
      const self = this
      const payload = {
        subject: this.subject,
        name: this.name,
        email: this.email,
        message: this.message
      }
      console.log(payload)
      const url = process.env.GRIDFUL_CONTACTHOOK
      console.log(url)
      // return
      fetch(process.env.GRIDFUL_CONTACTHOOK, {
        method: 'post',
        body: JSON.stringify(payload)
      }).then(function(response) {
        return response.json();
      }).then(function(data) {
          console.log('Contact success:', data)
          self.$router.push('/thanks')
      }).catch(function (error) {
        console.log(error)
        self.$router.push('/oops')
      })

          /*
      axios.post(url, payload)
        .then(() => {
          console.log('contact success')
          self.$router.push('/thanks')
        })
        .catch(function (error) {
          console.log(error)
          self.$router.push('/oops')
        })
      */
    }
  }
}
</script>
