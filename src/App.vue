<template>
  <EntrySection :addToNotes='addToNotes' :notes='notes' @add-note="addToNotes"/>
  <NotesSection :notes='notes' :deleteNote='deleteNote' />
</template>

<script>
import EntrySection from './components/EntrySection.vue'
import NotesSection from './components/NotesSection.vue'
export default {
  name: 'App',
  components: {
    EntrySection,
    NotesSection
  },
  data: function () {
    return {
      notes: {}
    }
  },
  methods: {
    addToNotes: function (text) {
      this.notes.data.push({ id: this.notes.length, text: text })
      localStorage.setItem('notesData', JSON.stringify(this.notes))
    },
    deleteNote: function (id) {
      this.notes.data.splice(id, 1)
      localStorage.setItem('notesData', JSON.stringify(this.notes))
    }
  },
  mounted: function () {
    const data = localStorage.getItem('notesData')
    if (data) {
      this.notes = JSON.parse(data)
    } else {
      localStorage.setItem('notesData', JSON.stringify({ data: [] }))
      window.location.reload()
    }
  }
}
</script>
