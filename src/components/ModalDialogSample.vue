<template>
  <div class="ModalDialogSampleBase">
    <h1>{{ msg }}</h1>
    <button @click="show">ダイアログの表示</button>
    <div class="message-field">ダイアログ入力メッセージ<br>{{message}}</div>
    <ModalDialog v-if="showDialog" @ok='ok' @cancel='cancel'/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import ModalDialog from './ModalDialog.vue';

@Component({
  components: {
    ModalDialog,
  },
})
export default class ModalDialogSample extends Vue {
  name: string = 'ModalDialogSample';
  msg: string = 'モーダルダイアログのサンプル';
  message: string = '';
  showDialog: boolean = false;
  show(): void {
    this.showDialog = true;
  }
  ok(message: string): void {
    this.showDialog = false;
    this.message = message;
  }
  cancel(): void {
    this.showDialog = false;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.message-field {
  height: auto;
  width: auto;
  margin-top: 10px;
  font-size: x-large;
}
</style>
