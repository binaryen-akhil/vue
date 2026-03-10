<template>
  <div>
    <h1>{{message}}</h1>

  </div>
</template>
<script>
  export default{
    setup(){
      const message = 'Hello World'
      return{
        message
      }
    }
  }
</script>