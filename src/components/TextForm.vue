<template>
  <h1>{{ heading }}</h1>
  <div class="mb-3">
    <textarea class="form-control" rows="12" v-model="text"></textarea>
  </div>
  <button class="btn btn-danger" @click="copy">Copy Text</button>
  <button class="btn btn-primary mx-3" @click="uppercase">
    Convert To UpperCase
  </button>
  <button class="btn btn-primary" @click="lowercase">
    Convert To LowerCase
  </button>
  <button class="btn btn-danger mx-3" @click="clr">
    Clear Field
  </button>
  <div className="container my-3">
    <h1>Text Summary</h1>
    <p>{{text.split(' ').length}} Words {{text.length}} Characters</p>
    <p>Read Time {{0.008 * text.split(' ').length}} Minutes</p>
  </div>
</template>

<script>
export default {
  name: "TextForm",
  props: {
    heading: String,
  },
  data() {
    return {
      text: "",
    };
  },
  methods: {
    copy() {
        let newText = this.text;
        navigator.clipboard.writeText(newText);
        this.$emit('true')
    },
    uppercase() {
      let newText = this.text.toUpperCase();
      this.text = newText;
    },
    lowercase() {
      let newText = this.text.toLowerCase();
      this.text = newText;
    },
    clr() {
      this.text = '';
    },
  },
  emits: ['true']
};
</script>
