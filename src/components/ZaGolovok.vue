<template>
  <div
    class="relative flex w-full flex-col items-center justify-center overflow-hidden bg-background md:shadow-xl h-screen"
  >
    <motion.span
      class="pointer-events-none whitespace-pre-wrap bg-gradient-to-b from-gray-300/80 to-black bg-clip-text text-center text-8xl font-medium leading-none text-transparent dark:from-white dark:to-slate-400/10"
      :initial='{ transform: "translateY(-100px)" }'
      :animate='{ transform: "translateY(0px)" }'
      :transition='{ type: "spring", duration: 1.5 }'
    >
      Приложение
      <br>
      <span class="font-bold">
        "Честный знак"
      </span>
    </motion.span>
    <ParticlesBg
      class="absolute inset-0 h-screen"
      :quantity="100"
      :ease="100"
      :color="isDark ? '#FFF' : '#000'"
      :staticity="10"
      refresh
    />
  </div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import { useColorMode } from "@vueuse/core";
import ParticlesBg from "@/components/ui/particles-bg/ParticlesBg.vue";
import { motion } from "motion-v";

const isDark = computed(() => useColorMode().value == "dark");
</script>
