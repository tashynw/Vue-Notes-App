<template>
	<div class="notes-container">
    <div v-for="(note,i) in notes.data" class="note-box" :key="i">
      <p class="note-text">{{ note.text }}</p>
      <img src="@/assets/delete.png" width="25" height="25" @click="deleteNote(i)"/>
    </div>
    <p v-if="notes.data && notes.data.length===0">No posts available...</p>
  </div>
</template>
<script>
export default {
  name: 'NotesSection',
  props: ['notes', 'addToNotes', 'deleteNote']
}
</script>
