<template>
  <div id="staff" class="staff-container">
    <div class="staff-spotlight full-width-banner">
      <p class="paragraph">SITCON 年會每年皆是許多志工奉獻與時間精神所舉辦；若你對參與 SITCON 年會的籌備有興趣，歡迎填寫表單，我們將在明年活動開始籌備時通知您！</p>
      <p class="paragraph">
        <a
          href="https://forms.gle/1J9fxQP2ux55PJXC9"
          class="tone-trans form-link font-bold"
          target="_blank"
          rel="noopener"
        >表單連結</a>
      </p>
    </div>
    <div
      v-for="group in staffs"
      :key="`staff-group-${group.name}`"
      class="staff-spotlight staff-group"
    >
      <h2 class="staff-group-name font-bold">{{ group.name }}</h2>
      <p class="paragraph staff-group-intro">{{ group.description }}</p>
      <div class="staff-wrapper">
        <div
          v-for="member in group.members"
          :key="`${group.name}-${member.name}`"
          class="staff"
        >
          <img
            class="staff-avatar"
            :src="`https://www.gravatar.com/avatar/${member.emailHash}?s=320&d=https://sitcon.org/2020/img/sitcon-logo.png&r=g`"
            :alt="`${member.name}'s Avatar`"
          />
          <p>{{ member.name }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

import staffData from '@/../public/json/staff.json';

@Component
export default class Staff extends Vue {
  private staffs = staffData;
}
</script>
