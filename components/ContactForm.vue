<template>
  <div class="container mx-auto">
    <form class="w-full" @submit.prevent="submitForm">
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
          <InputField
            type="text"
            label="Name"
            :value="formData.name"
            @input="formData.name = $event"
          />
        </div>
        <div class="w-full md:w-1/2 px-3">
          <InputField
            type="email"
            label="Email"
            :value="formData.email"
            @input="formData.email = $event"
          />
        </div>
      </div>
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full md:w-1/2 px-3">
          <InputField
            type="text"
            label="Phone"
            :value="formData.phone"
            @input="formData.phone = $event"
          />
        </div>
        <div class="w-full md:w-1/2 px-3">
          <InputField
            type="text"
            label="Subject"
            :value="formData.subject"
            @input="formData.subject = $event"
          />
        </div>
      </div>
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <TextareaField
            label="Message"
            :value="formData.message"
            @input="formData.message = $event"
          />
        </div>
        <div class="flex justify-center w-full px-3">
          <button
            class="shadow bg-indigo-600 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-6 rounded"
            type="submit"
          >
            Send Message
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import InputField from "./InputField.vue";
import TextareaField from "./TextareaField.vue";
export default {
  components: { InputField, TextareaField },
  data() {
    return {
      formData: {
        name: "",
        email: "",
        phone: "",
        subject: "",
        message: "",
      },
    };
  },
  methods: {
    submitForm() {
      console.log(this.formData);
      this.formData = {
        name: "",
        email: "",
        phone: "",
        subject: "",
        message: "",
      };
    },
  },
};
</script>

<style></style>
