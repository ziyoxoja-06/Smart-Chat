<template>
  <q-page class="flex column">
    <div class="q-pa-md column col justify-end">
      <q-chat-message
        v-for="message in messages"
        :key="message.text"
        :name="message.from"
        :text="[message.text]"
        :sent="message.from === 'me'"
      />
    </div>
    <q-footer elevated>
      <q-toolbar>
        <q-form @submit="sendMessage" class="flex full-width">
          <q-input
            v-model="newMessage"
            bg-color="white"
            class="col"
            rounded
            outlined
            label="Message"
            dense
          >
          </q-input>
          <q-btn round dense flat type="submit" color="white" icon="send" />
        </q-form>
      </q-toolbar>
    </q-footer>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      newMessage: "",
      messages: [
        {
          text: "hey Jim, how are you?",
          from: "me",
        },
        {
          text: "Good, how about you?",
          from: "them",
        },
        {
          text: "I am fine, thanks!",
          from: "me",
        },
      ],
    };
  },

  methods: {
    sendMessage() {
      console.log('sdsd');
      this.messages.push({
        text: this.newMessage === "" ? "ss" : this.newMessage,
        from: "me",
      });
    },
  },
};
</script>
