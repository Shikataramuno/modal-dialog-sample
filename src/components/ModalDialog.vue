<template>
  <transition name="modal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container">
          <div class="modal-header">モーダルダイアログ
          </div>
          <div class="modal-body">
            <input type='text' v-model='message' placeholder="メッセージ入力欄です">
          </div>
          <div class="modal-footer">
            <button class="modal-default-button" @click='ok(message)'>OK</button>
            <button class="modal-default-button" @click='cancel()'>Cancel</button>
          </div>
        </div>
      </div>
    </div>
  </transition>
</template>

<script lang="ts">
import { Component, Emit, Vue } from 'vue-property-decorator';

export default class ModalDialog extends Vue {
  message: string = '';

  @Emit('ok')
  ok(str: string): void {
    //
  }

  @Emit('cancel')
  cancel(): void {
    //
  }
}
</script>

<style>
@import '../style/modal.css'
</style>
