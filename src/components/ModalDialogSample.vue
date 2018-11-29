<template>
  <div class="ModalDialogSampleBase">
    <h1>{{ msg }}</h1>
    <button @click="show" :diable='!showDialog'>ダイアログの表示</button>
    <div>{{message}}</div>
    <ModalDialog v-if="showDialog" @ok='ok' @cancel='cancel'/>
  </div>

</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import ModalDialog from './ModalDialog.vue';

@Component({
  components: {
    ModalDialog,
  },
})
export default class ModalDialogSample extends Vue {
  name: string = 'ModalDialogSample';
  message: string = '';
  showDialog: boolean = false;
  @Prop() private msg!: string;
  // computed
  // methods
  show(): void {
    console.log('showDialog');
    this.showDialog = true;
  }
  ok(message: string): void {
    console.log('close with OK');
    console.log(message);
    this.showDialog = false;
    this.message = message;
  }
  cancel(): void {
    console.log('close with Cancel');
    this.showDialog = false;
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
