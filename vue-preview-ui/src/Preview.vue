<script setup>

import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";
import { AspectRatio } from "@/components/ui/aspect-ratio";
import { Check } from "lucide-vue-next";

const features = [
  { icon: "📱", text: "OPPO 手机 0 元电池券免费抽" },
  { icon: "🔋", text: "街电充电 1 小时免费限量领" },
  { icon: "🔌", text: "Type-C 闪充数据线限量领" },
];
</script>

<template>
  <div class="bg-green-100 p-6 rounded-lg shadow-lg">
    <div class="flex justify-between items-center mb-4">
      <img src="https://via.placeholder.com/100x50" alt="Logo" />
      <Badge class="bg-black text-white">守护满格生活</Badge>
    </div>
    <Card class="mb-6">
      <CardHeader>
        <CardTitle class="text-4xl font-extrabold text-black">
          OPPO 续航计划 <span class="text-green-800">2022</span>
        </CardTitle>
      </CardHeader>
      <CardContent class="text-lg text-green-700">
        电池换新一口价 限时 <span class="text-green-900 font-bold">39</span> 元起
        <br />
        OPPO 商城配件 秒杀低至 <span class="text-green-900 font-bold">6.9</span> 元
      </CardContent>
    </Card>
    <AspectRatio :ratio="16 / 9" class="mb-6">
      <img
        src="https://via.placeholder.com/800x450"
        alt="Promotional Image"
        class="rounded-md object-cover"
      />
    </AspectRatio>
    <div class="bg-white p-4 rounded-lg shadow-md">
      <div class="text-center text-green-800 font-bold mb-4">
        9 月 25 日 ~ 11 月 30 日
      </div>
      <div class="text-center text-xl font-semibold mb-4">
        多重续航福利限量放送
      </div>
      <ul class="space-y-2">
        <li v-for="feature in features" :key="feature.text" class="flex items-center">
          <Check class="text-green-600 mr-2" />
          <span>{{ feature.text }}</span>
        </li>
      </ul>
    </div>
    <div class="text-sm text-gray-600 mt-6">
      <p>备注：</p>
      <ol class="list-decimal list-inside">
        <li>“电池换新一口价”是指保外更换电池时，仅收取电池备件费用，免收 50 元人工费；</li>
        <li>前往 OPPO 官方服务中心或选择寄修，同城取送均可享受折扣价格，“同城取送”所产生的服务费需另行收取；</li>
        <li>本活动折扣不支持与 OPPO 会员&一加成长会员的维修折扣同享；</li>
        <li>参与活动更换后的电池享受 180 天官方保修服务；</li>
        <li>基于环保原则，维修更换下的故障部件将由 OPPO 官方服务中心统一回收处理；</li>
        <li>为保证服务体验，建议到访前电话咨询 OPPO 官方服务中心或拨打 95018 官方服务热线了解活动详情及库存，并提前预约。</li>
      </ol>
    </div>
  </div>
</template>

<style scoped>
.bg-green-100 {
  background-color: #e6f7e6;
}
.text-green-800 {
  color: #2f855a;
}
.text-green-700 {
  color: #38a169;
}
.text-green-900 {
  color: #22543d;
}
</style>