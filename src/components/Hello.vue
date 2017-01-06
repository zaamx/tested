<template>
  <div class="hello">
    <vf-form action="process-form" method="POST" :validation="validation" > //:options="options"
    <vf-status-bar ref="statusbar"></vf-status-bar>
    <vf-text label="User name:"  name="username" ref="username"></vf-text>
    <vf-password label="Password:"  name="password" ref="password"></vf-password>
    <vf-file label="Upload file"
           name="upload_file"
           v-ref:upload_file></vf-file>
    <vf-submit></vf-submit>
  </vf-form>
  </div>
</template>

<script>
import Vue from 'vue'
import VueForm from 'vue-form-2'

Vue.use(VueForm, {
  layout: 'form-horizontal'
})

export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      validation: {
        rules: {
          username: {
            required: true,
            min: 4
          },
          password: {
            required: true
            // between: [0, 120]
          }
          // about: {
          //   max: 200
          // },
          // smaller_than_age: {
          //   smallerThan: 'age'
          // },
          // graduation_date: {
          //   greaterThan: 'birth_date'
          // },
          // married_years: {
          //   requiredIf: 'married',
          //   min: 0
          // }
        }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
