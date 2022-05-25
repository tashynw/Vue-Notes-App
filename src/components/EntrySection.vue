<template>
    <div class="entry-form">
        <input class="entry-input" placeholder="Add new note" v-model="noteInput"/>
        <img src="@/assets/plus.png" width="25" height="25" @click="addToNotes(noteInput)" />
    </div>
</template>
<script>
export default {
  name: 'EntrySection',
  props: ['addToNotes'],
  data () {
    return {
      noteInput: ''
    }
  }
}
</script>
