<template>
  <WavyBackground class="relative flex h-[500px] w-full flex-col overflow-hidden p-6">
    <a href="https://github.com/samrejnor/leto_konec_smena" target="_blank" class="flex flex-col items-center justify-center m-5">
      <InteractiveHoverButton text="Скачать" />
    </a>
    <AnimatedList>
      <template #default>
        <Notification
          v-for="(item, idx) in notifications"
          :key="idx"
          :name="item.name"
          :description="item.description"
          :icon="item.icon"
          :color="item.color"
          :time="item.time"
        />
      </template>
    </AnimatedList>
  </WavyBackground>
</template>

<script setup lang="ts">
import { InteractiveHoverButton } from './ui/interactive-hover-button';
import { WavyBackground } from './ui/wavy-background/';

const notifications = [
  {
    name: "Скорость",
    description: "Всё выполняется в районе 10 секунд",
    time: "Вот это скорость",
    icon: "💸",
    color: "#00C9A7",
  },
  {
    name: "Точность",
    description: "Нейросеть определяет состав правильно с точностью до 99.9%",
    time: "Очень точно!",
    icon: "🎯",
    color: "#FF3D71",
  },
  {
    name: "GUI клиент",
    description: "Не нужно разбираться в устройстве терминала, загрузил – и готово!",
    time: "Вау!",
    icon: "🖥️",
    color: "#1E86FF",
  },
  {
    name: "Вредно или нет?",
    description: "Поможет определить полезность продукта по составу",
    time: "Фух...",
    icon: "✅",
    color: "#45B26B",
  },
  {
    name: "Всё сохраняется!",
    description: "Вы сможете посмотреть предыдущие разборы, чтобы сравнивать продукты.",
    time: "Ничто не пропадёт!",
    icon: "💾",
    color: "#45B26B",
  },
];
</script>
