<template>
<div><p><h1>PoetryDB is an API for internet poets.</h1>
This repo contains collection of Quran Translations and to allow development of websites, apps etc, it is structured in REST Architectural Style. The purpose of this repo is to spread the word of God everywhere in the world.</p>
</div>
<div>
  <p>
    Это репо содержит коллекцию переводов Корана для обеспечения возможности разработки веб-сайтов, приложений и т.д., оно структурировано в архитектурном стиле REST. Цель этого отчета - распространить слово Божье по всему миру.
  </p>
</div>
<br>
<div class="container">
    <div class="def-lvl1" v-for="value in items" :key="value.items">
        <div class="inside">
          <h3>{{value.name}}</h3> <br>
        Автор: {{value.author}} <br>
        Язык: {{value.language}} <br>
        Источник: {{value.source}} <br>
      </div>
    </div>
  </div>
</template>

<script lang="ts">

import axios from 'axios'
  export default {
    name: 'Items',
    data(){
      return {
        items: [],
        errors: []
      }
    },
    created(){
      axios.get('https://cdn.jsdelivr.net/gh/fawazahmed0/quran-api@1/editions.json')
      .then(responce => {
        this.items = responce.data
        console.log(responce)
      })
      .catch(e=>{
        this.errors.push(e)
      })
    }
  }
</script>
