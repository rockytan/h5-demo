<script setup>

import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";
import { Button } from "@/components/ui/button";
import { AspectRatio } from "@/components/ui/aspect-ratio";
import { Separator } from "@/components/ui/separator";
import { Check } from "lucide-vue-next";
</script>

<template>
  <div class="bg-green-100 min-h-screen p-6">
    <div class="max-w-2xl mx-auto">
      <Card class="mb-6">
        <CardHeader>
          <CardTitle class="text-3xl font-bold text-center">
            OPPO 续航计划 2022
          </CardTitle>
        </CardHeader>
        <CardContent>
          <AspectRatio :ratio="16 / 9">
            <img
              src="https://via.placeholder.com/800x450"
              alt="Oppo Event"
              class="rounded-md object-cover"
            />
          </AspectRatio>
          <div class="text-center mt-4">
            <Badge class="bg-green-500 text-white">守护满格生活</Badge>
            <p class="mt-2 text-lg">
              电池焕新一口价 限时 <span class="text-green-600">39</span> 元起
            </p>
            <p class="text-lg">
              OPPO 商城配件 秒杀低至 <span class="text-green-600">6.9</span> 元
            </p>
          </div>
        </CardContent>
      </Card>

      <Card>
        <CardContent>
          <div class="text-center mb-4">
            <p class="text-xl font-semibold">多重续航福利限量放送</p>
            <p class="text-sm text-gray-600">9月25日 ~ 11月30日</p>
          </div>
          <Separator />
          <ul class="mt-4 space-y-4">
            <li class="flex items-center">
              <Check class="text-green-500 mr-2" />
              OPPO 手机 0 元电池券免费抽
            </li>
            <li class="flex items-center">
              <Check class="text-green-500 mr-2" />
              街电充电 1 小时免费限量领
            </li>
            <li class="flex items-center">
              <Check class="text-green-500 mr-2" />
              Type-C 闪充数据线限量领
            </li>
          </ul>
          <Button class="mt-6 w-full bg-green-500 text-white">
            了解更多
          </Button>
        </CardContent>
      </Card>
    </div>
  </div>
</template>