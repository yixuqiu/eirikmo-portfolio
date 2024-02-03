<script setup lang="ts">
import { toRefs } from "vue";
import ExperienceCard from "../ExperienceCard.vue";
import AngularIcon from "../icons/AngularIcon.vue";
import CSharpIcon from "../icons/CSharpIcon.vue";
import DotNetIcon from "../icons/DotNetIcon.vue";
import SqlIcon from "../icons/SqlIcon.vue";
import TypeScriptIcon from "../icons/TypeScriptIcon.vue";
import TechIcon from "../TechIcon.vue";

const props = defineProps<{
  onClick: () => void;
  onMouseOver: () => void;
  onMouseLeave: () => void;
}>();

const { onClick, onMouseOver, onMouseLeave } = toRefs(props);
</script>

<template>
  <ExperienceCard
    ref="webtopRef"
    v-motion-fade-visible-once-custom
    :on-click="onClick"
    :on-mouse-over="onMouseOver"
    :on-mouse-leave="onMouseLeave"
  >
    <template #logo>
      <img src="/images/work/webtop/logo.png" alt="Webtop Logo" class="select-none w-full" />
    </template>
    <template #default>
      <div class="text-base leading-7 text-white/90 w-full">
        <h1 class="text-2xl font-bold">Webtop Solutions</h1>
        <h2 class="text-lg font-semibold text-red-500 break-words wrap">CRM and Digital Real-Estate Solution</h2>
        <h2 class="text-lg font-light italic text-sky-200 break-words wrap">Jul 2016 - Dec 2018 · 2 yrs 6 mos</h2>
        <h3 class="text-lg font-light text-zinc-200 break-words wrap mt-2">System Developer</h3>
        <h3 class="text-lg font-bold">Full-time Employment · Trondheim, Norway</h3>
      </div>
    </template>

    <template #tech>
      <TechIcon v-slot="slotProps" href="https://www.typescriptlang.org/" name="TypeScript" :size="24">
        <TypeScriptIcon :height="slotProps.height" :width="slotProps.width" />
      </TechIcon>

      <TechIcon v-slot="slotProps" href="https://angularjs.org/" name="AngularJS" :size="24">
        <AngularIcon :height="slotProps.height" :width="slotProps.width" />
      </TechIcon>

      <TechIcon v-slot="slotProps" href="https://learn.microsoft.com/en-us/dotnet/csharp/" name="C#" :size="24">
        <CSharpIcon :height="slotProps.height" :width="slotProps.width" />
      </TechIcon>

      <TechIcon v-slot="slotProps" href="https://www.mysql.com/" name="MySQL" :size="24">
        <SqlIcon :height="slotProps.height" :width="slotProps.width" />
      </TechIcon>

      <TechIcon v-slot="slotProps" href="https://dotnet.microsoft.com/en-us/" name=".Net" :size="24">
        <DotNetIcon :height="slotProps.height" :width="slotProps.width" />
      </TechIcon>
    </template>
  </ExperienceCard>
</template>