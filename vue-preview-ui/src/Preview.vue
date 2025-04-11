<script setup>

import { ref } from 'vue';
import { Button } from '@/components/ui/button';
import { Input } from '@/components/ui/input';
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';
import { Avatar, AvatarImage, AvatarFallback } from '@/components/ui/avatar';
import { Tabs, TabsList, TabsTrigger, TabsContent } from '@/components/ui/tabs';
import { Search } from 'lucide-vue-next';

const knowledgeBases = ref([
  { title: '公司制度', description: '公司规章制度，手册等', date: '2024/11/25 21:08更新' },
  { title: '公司制度', description: '公司规章制度，手册等', date: '2024/11/25 21:08更新' },
  { title: '公司制度', description: '公司规章制度，手册等', date: '2024/11/25 21:08更新' },
]);
</script>

<template>
  <div class="flex h-screen bg-gray-100">
    <!-- Sidebar -->
    <aside class="w-64 bg-white shadow-md">
      <div class="p-4 text-xl font-bold text-center text-pink-600">平台名称</div>
      <nav class="mt-4">
        <ul>
          <li class="p-2 hover:bg-gray-200">Dashboard</li>
          <li class="p-2 hover:bg-gray-200">智能体管理</li>
          <li class="p-2 hover:bg-gray-200">工具管理</li>
          <li class="p-2 bg-gray-200 font-bold">知识库管理</li>
          <li class="p-2 hover:bg-gray-200">工作流管理</li>
          <li class="p-2 hover:bg-gray-200">模型接入</li>
          <li class="p-2 hover:bg-gray-200">模型配置</li>
          <li class="p-2 hover:bg-gray-200">团队管理</li>
          <li class="p-2 hover:bg-gray-200">角色权限</li>
          <li class="p-2 hover:bg-gray-200">帮助与反馈</li>
        </ul>
      </nav>
      <div class="p-4">
        <Avatar>
          <AvatarImage src="https://via.placeholder.com/150" />
          <AvatarFallback>用户</AvatarFallback>
        </Avatar>
      </div>
    </aside>

    <!-- Main Content -->
    <main class="flex-1 p-6">
      <div class="flex justify-between items-center mb-4">
        <Tabs default-value="all">
          <TabsList>
            <TabsTrigger value="all">全部</TabsTrigger>
            <TabsTrigger value="department">所属部门</TabsTrigger>
            <TabsTrigger value="type">文档类型</TabsTrigger>
            <TabsTrigger value="date">更新时间</TabsTrigger>
          </TabsList>
        </Tabs>
        <div class="flex items-center space-x-2">
          <Button variant="outline">+创建知识库</Button>
          <div class="relative">
            <Input placeholder="搜索" class="pl-10" />
            <Search class="absolute left-3 top-1/2 transform -translate-y-1/2 text-gray-400" />
          </div>
        </div>
      </div>

      <div class="grid grid-cols-3 gap-4">
        <Card v-for="(kb, index) in knowledgeBases" :key="index">
          <CardHeader>
            <CardTitle>{{ kb.title }}</CardTitle>
          </CardHeader>
          <CardContent>
            <div class="flex items-center space-x-2">
              <Avatar>
                <AvatarImage src="https://via.placeholder.com/50" />
                <AvatarFallback>图</AvatarFallback>
              </Avatar>
              <div>
                <p>{{ kb.description }}</p>
                <p class="text-sm text-gray-500">{{ kb.date }}</p>
              </div>
            </div>
            <div class="flex justify-between mt-4 text-pink-600">
              <span>浏览</span>
              <span>引用</span>
              <span>设置</span>
              <span>删除</span>
            </div>
          </CardContent>
        </Card>
      </div>
    </main>
  </div>
</template>

<style scoped>
/* Add any additional styles here */
</style>