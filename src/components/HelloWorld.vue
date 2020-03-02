<template>
  <div>
    <input type="text" placeholder="输入新科目" @keyup.enter="addSubject" />
    <ul>
      <li v-for="subject in subjects" :key="subject">{{subject}}</li>
    </ul>
  </div>
</template>
<script lang='ts'>
import { Component, Vue } from "vue-property-decorator";
@Component
export default class Hello extends Vue {
  subjects: string[];
  constructor() {
    super();
    this.subjects = ["语文", "数学"];
  }
  private addSubject(event: any) {
    console.log(event);
    this.subjects.push(event.target.value);
    event.target.value = "";
  }
}
</script>
