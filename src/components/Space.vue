<template>
  <div class="space">
    <h1>{{ msg }}</h1>
    <div class="demo-split" ref="splitElement">
      <Split v-model="split">
        <div slot="left" class="demo-split-pane">
          <Input
            v-model="input"
            type="textarea"
            class="textarea-input"
            :autosize="{minRows: minRows, maxRows: maxRows}"
            show-word-limit
            placeholder="请输入内容"
          />
        </div>
        <div slot="right" class="demo-split-pane">
          <Input
            v-model="output"
            class="textarea-input"
            type="textarea"
            :autosize="{minRows: minRows, maxRows: maxRows}"
            show-word-limit
            readonly
            style="padding-left: 5px; padding-right: 0px;"
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
      minRows: 25,
      maxRows: 28,
      title: "空格处理",
      input: null,
      output: null
    };
  },
  beforeCreate() {
    this.minRows = 28;
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
  position: absolute;
  top: 80px;
  left: 20px;
  right: 20px;
  bottom: 20px;
  border: 1px solid #dcdee2;
}

.demo-split-pane {
  padding: 10px;
  height: 100%;
}
.ivu-input-wrapper {
  /* height: 100%; */
}
</style>
