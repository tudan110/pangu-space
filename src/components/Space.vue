<template>
  <div class="space">
    <h1>{{ msg }}</h1>
    <div class="demo-split">
      <Split v-model="split">
        <div slot="left" class="demo-split-pane">
          <Input v-model="input" type="textarea" :autosize="{minRows: 30}" placeholder="请输入内容" />
        </div>
        <div slot="right" class="demo-split-pane">
          <Input
            v-model="output"
            type="textarea"
            :autosize="{minRows: 30}"
          />
        </div>
      </Split>
    </div>
  </div>
</template>

<script>
const pangu = require("pangu");

export default {
  name: "Space",
  props: {
    msg: String
  },
  data() {
    return {
      split: 0.5,
      title: "空格处理",
      input: null,
      output: null
    };
  },
  watch: {
    input() {
      this.output = pangu.spacing(this.input);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.demo-split {
  height: 660px;
  border: 1px solid #dcdee2;
}
.demo-split-pane {
  padding: 10px;
}
</style>
