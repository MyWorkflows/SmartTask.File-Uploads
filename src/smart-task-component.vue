<script lang="ts">
import { defineComponent } from "vue";


export default /*#__PURE__*/ defineComponent({
  name: "SmartTaskComponent", // vue component name
  props: ['componentState', 'componentStatus'],
  data() {
    return { model: {} };
  },
  computed: {},
  methods: {
    async submitForm() {
      this.$emit("execute-smart-task", this.model);
    },
  },
  created() {
    if (this.componentState) {
      this.model = this.componentState;
    }
  },
  setup() {},
});
</script>

<template>
 <form>
    <div class="row">
      <div class="col">
       <label for="formFileMultiple" class="form-label">Select Files</label>
        <input class="form-control" type="file" id="formFileMultiple" multiple />
      </div>

    </div>
    <div class="my-5">
      <button
        type="button"
        @click="submitForm"
        class="float-end btn btn-success"
      >
        Save and complete
      </button>
    </div>
  </form>
</template>

