<template>
  <div class="row">

      <input v-model="newContact" placeholder="Name" type="text" />
      <button  style="padding-top: 10px; margin-bottom: 20px;" @click="addContact">Add Contact</button>

      <button  @click="sortContracts">Sort</button>


   	<transition-group name="slide-up" tag="ul" appear>
          <li v-for="contact in contacts" :key="contact">
            {{ contact }}
          </li>
        </transition-group>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newContact: '',
      contacts: ['Beau Thabeast', 'Cindy Rella', 'Alice Wunderlind']
    }
  },
  methods: {
    addContact() {
      this.contacts.push(this.newContact)
      this.newContact = ''
    },
    sortContracts(){
      this.contacts = this.contacts.sort()

    }
  }
}
</script>

<style>
  button {
    font-size: 14px;
    width: 5em;
    height: 3em;

  }

  input {
    height: 2em;
  }

  ul{
    list-style-type: none
  };
</style>
