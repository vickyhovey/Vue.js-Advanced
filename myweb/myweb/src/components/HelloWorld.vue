<!-- 组件格式
template:组件html内容
script:组件js脚本(ES6)
style:组件css样式单 -->
<template>
  <div class="hello">
    <pre>{{content}}</pre>
    <h1>Hello World!</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      content: ""
    };
  },
  mounted() {
    this.axios.post("http://api.komavideo.com/news/list").then(body => {
      this.content = body.data;
    });
  }
};
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
