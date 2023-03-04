<template>
  <div class="note"
    @mouseover="onMouseOver"
    @mouseleave="onMouseLeave"
    v-bind:class="{mouseover:note.mouseover}">
    <div class="note-icon">
      <i class="fas fa-file-alt"></i>
    </div>
    <div class="note-name">{{note.name}}</div>
  </div>
</template>

<script>
export default {
  name: 'NoteItem',
  props: [
    'note',
  ],
  methods:{
    onMouseOver:function(){
      this.note.mouseover = true;
    },
    onMouseLeave:function(){
      this.note.mouseover = false;
    }
  }
}
</script>

<style scoped lang="scss">
.note {
  margin: 10px 0;
  display: flex;
  align-items: center;
  padding: 5px;
  color: rgba(25, 23, 17, 0.6);
  &.mouseover {
    background-color: rgb(232, 231, 228);
    cursor: pointer;
  }
  .note-icon {
    margin-left: 10px;
  }
  .note-name {
    width: 100%;
    padding: 3px 10px;
  }
}
</style>
