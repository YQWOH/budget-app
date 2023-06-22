<template>
  <div class="flex items-center">
    <span :class="`material-icons ${transClass}`">{{ transIcon }}</span>
    <p>{{ transText }}</p>
  </div>
  <div class="flex items-center">
    <p :style="'margin-right:10px; color: ' + transColor">{{ transType }} {{ transCurrent }}</p>
    <button :id="transId" class="transaction__bin" @click="deleteTrans($event)">
      <span class="material-icons">delete</span>
    </button>
  </div>
</template>

<script>
export default {
  name: "Transaction",
  props: {
    transClass: {
      type: String,
      default: "",
    },
    transIcon: {
      type: String,
      default: "",
    },
    transColor: {
      type: String,
      default: "",
    },
    transType: {
      type: String,
      default: "",
    },
    transCurrent: {
      type: String,
      default: "",
    },
    transText: {
      type: String,
      default: "",
    },
    transId: {
      type: Number,
      default: null,
    },
  },
  methods: {
    deleteTrans(e) {
      console.log("delete");
      console.log("e: ", e.target.parentElement.id);
      this.$emit("deleteTransaction", e.target.parentElement.id)
    },
  },
};
</script>