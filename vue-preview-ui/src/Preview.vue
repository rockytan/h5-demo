<script setup>

import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Badge } from "@/components/ui/badge";
import { AspectRatio } from "@/components/ui/aspect-ratio";
import { Separator } from "@/components/ui/separator";
import { Avatar, AvatarImage } from "@/components/ui/avatar";
</script>

<template>
  <div class="bg-pink-100 p-6 rounded-lg space-y-6">
    <Card class="bg-gradient-to-r from-pink-200 to-pink-300 shadow-lg">
      <CardHeader>
        <CardTitle class="text-center text-pink-800 text-2xl font-bold">
          天猫38节 · 稀缺货源
        </CardTitle>
      </CardHeader>
    </Card>

    <Card class="bg-white shadow-md rounded-lg">
      <CardContent class="flex items-center justify-between p-4">
        <div>
          <h2 class="text-xl font-bold text-pink-900">限量爆款 半价优惠</h2>
          <p class="text-sm text-pink-700">即日起至3月4日晚8点</p>
          <Badge class="bg-pink-500 text-white mt-2">查看规则</Badge>
        </div>
        <AspectRatio :ratio="1">
          <img
            src="https://via.placeholder.com/100"
            alt="Product"
            class="rounded-md"
          />
        </AspectRatio>
      </CardContent>
    </Card>

    <Card class="bg-white shadow-md rounded-lg">
      <CardContent class="flex items-center justify-between p-4">
        <div>
          <h2 class="text-xl font-bold text-pink-900">前100名购机 返现金红包</h2>
          <p class="text-sm text-pink-700">3月4日20:00起</p>
          <Badge class="bg-pink-500 text-white mt-2">查看详情</Badge>
        </div>
        <AspectRatio :ratio="1">
          <img
            src="https://via.placeholder.com/100"
            alt="Product"
            class="rounded-md"
          />
        </AspectRatio>
      </CardContent>
    </Card>

    <Separator class="my-4" />

    <Card class="bg-white shadow-md rounded-lg">
      <CardContent class="flex items-center justify-between p-4">
        <div>
          <h2 class="text-xl font-bold text-pink-900">人气口碑爆款 NEW Z6X</h2>
          <p class="text-sm text-pink-700">0.3"DMD芯片 | 面面出色</p>
          <Button variant="outline" class="text-pink-800 border-pink-500 mt-2">
            立即购买
          </Button>
        </div>
        <Avatar>
          <AvatarImage src="https://via.placeholder.com/100" />
        </Avatar>
      </CardContent>
    </Card>

    <Card class="bg-white shadow-md rounded-lg">
      <CardContent class="flex items-center justify-between p-4">
        <div>
          <h2 class="text-xl font-bold text-pink-900">业内高配旗舰 H3S</h2>
          <p class="text-sm text-pink-700">2200ANSI流明 | 亮度低蓝光认证</p>
          <Button variant="outline" class="text-pink-800 border-pink-500 mt-2">
            立即购买
          </Button>
        </div>
        <Avatar>
          <AvatarImage src="https://via.placeholder.com/100" />
        </Avatar>
      </CardContent>
    </Card>
  </div>
</template>