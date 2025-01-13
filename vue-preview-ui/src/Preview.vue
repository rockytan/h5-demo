<script setup>

import { Button } from "@/components/ui/button";
import { AspectRatio } from "@/components/ui/aspect-ratio";
import { ArrowRight } from "lucide-vue-next";
</script>

<template>
  <div class="flex flex-col items-center justify-center min-h-screen bg-green-100">
    <div class="text-center p-4">
      <h1 class="text-3xl font-bold mb-2">《都是老铁》</h1>
      <p class="text-xl mb-4">测测你和哪个大咖更铁</p>
      <p class="text-lg text-green-600">快手光合嘉年华</p>
    </div>
    <AspectRatio :ratio="9 / 16" class="w-full max-w-md mb-6">
      <img
        src="https://images.unsplash.com/photo-1588345921523-c2dcdb7f1dcd?w=800&dpr=2&q=80"
        alt="活动图片"
        class="rounded-md object-cover"
      />
    </AspectRatio>
    <Button variant="solid" class="flex items-center space-x-2">
      <span>开始测试</span>
      <ArrowRight />
    </Button>
  </div>
</template>

<style scoped>
h1 {
  color: #333;
}
</style>