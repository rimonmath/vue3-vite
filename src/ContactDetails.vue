<template>
  <div class="contact-details">
    <h1 class="contact-heading">Contact Details</h1>
    <p><strong> Name: </strong> {{ name }}</p>
    <p><strong> Website: </strong> {{ websiteAddress }}</p>
    <p><strong> Address: </strong> {{ address }}</p>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String
    },
    websiteAddress: {
      type: String,
      required: false,
      default: "http://yourwebsite.com"
    },
    address: {
      type: String,
      required: true
    }
  },
  data() {
    return {};
  }
};
</script>

<style scoped>
.contact-details {
  border: 1px solid gray;
  margin: 11px 22px;
  padding: 22px;
}

.contact-heading {
  color: rgb(0, 73, 107);
}
</style>
