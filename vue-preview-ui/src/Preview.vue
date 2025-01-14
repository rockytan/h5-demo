<script setup>

import { ref } from 'vue';
import { Input } from "@/components/ui/input";
import { Button } from "@/components/ui/button";
import { Alert, AlertDescription, AlertTitle } from "@/components/ui/alert";
import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectLabel,
  SelectTrigger,
  SelectValue,
} from "@/components/ui/select";

const form = ref({
  phone: '',
  consignee: '',
  areaCode: '',
  address: '',
  productId: '100102',
});

const provinces = ref([
  { code: '1001', name: '省1' },
  { code: '1002', name: '省2' },
]);

const cities = ref({
  '1001': [
    { code: '100101', name: '市1' },
    { code: '100102', name: '市2' },
  ],
  '1002': [
    { code: '100201', name: '市3' },
    { code: '100202', name: '市4' },
  ],
});

const districts = ref({
  '100101': [
    { code: '10010101', name: '区1' },
    { code: '10010102', name: '区2' },
  ],
  '100102': [
    { code: '10010201', name: '区3' },
    { code: '10010202', name: '区4' },
  ],
});

const selectedProvince = ref('');
const selectedCity = ref('');
const selectedDistrict = ref('');
const alertMessage = ref('');

const validateForm = () => {
  const phoneRegex = /^\d{11}$/;
  const consigneeRegex = /^[\u4e00-\u9fa5a-zA-Z]+$/;

  if (!form.value.consignee || !consigneeRegex.test(form.value.consignee)) {
    alertMessage.value = '请输入正确的收货人姓名';
    return false;
  }
  if (!form.value.phone || !phoneRegex.test(form.value.phone)) {
    alertMessage.value = '请输入正确的手机号';
    return false;
  }
  if (!form.value.address) {
    alertMessage.value = '请输入详细地址';
    return false;
  }
  return true;
};

const submitOrder = async () => {
  if (!validateForm()) return;

  form.value.areaCode = selectedDistrict.value;
  try {
    const response = await fetch('http://127.0.0.1:8080/api/order', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(form.value),
    });
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
};
</script>

<template>
  <div class="max-w-md mx-auto p-4 space-y-4">
    <div v-if="alertMessage" class="mb-4">
      <Alert>
        <AlertTitle>提示</AlertTitle>
        <AlertDescription>{{ alertMessage }}</AlertDescription>
      </Alert>
    </div>
    <div>
      <label for="consignee" class="block text-sm font-bold text-gray-700">收货人</label>
      <Input id="consignee" v-model="form.consignee" placeholder="请输入" />
    </div>
    <div>
      <label for="phone" class="block text-sm font-bold text-gray-700">手机号</label>
      <Input id="phone" v-model="form.phone" placeholder="请输入" />
    </div>
    <div>
      <label class="block text-sm font-bold text-gray-700">地址</label>
      <div class="flex space-x-2">
        <Select v-model="selectedProvince">
          <SelectTrigger>
            <SelectValue placeholder="省" />
          </SelectTrigger>
          <SelectContent>
            <SelectGroup>
              <SelectLabel>省份</SelectLabel>
              <SelectItem v-for="province in provinces" :key="province.code" :value="province.code">
                {{ province.name }}
              </SelectItem>
            </SelectGroup>
          </SelectContent>
        </Select>
        <Select v-model="selectedCity">
          <SelectTrigger>
            <SelectValue placeholder="市" />
          </SelectTrigger>
          <SelectContent>
            <SelectGroup>
              <SelectLabel>城市</SelectLabel>
              <SelectItem v-for="city in cities[selectedProvince]" :key="city.code" :value="city.code">
                {{ city.name }}
              </SelectItem>
            </SelectGroup>
          </SelectContent>
        </Select>
        <Select v-model="selectedDistrict">
          <SelectTrigger>
            <SelectValue placeholder="区" />
          </SelectTrigger>
          <SelectContent>
            <SelectGroup>
              <SelectLabel>区县</SelectLabel>
              <SelectItem v-for="district in districts[selectedCity]" :key="district.code" :value="district.code">
                {{ district.name }}
              </SelectItem>
            </SelectGroup>
          </SelectContent>
        </Select>
      </div>
    </div>
    <div>
      <label for="address" class="block text-sm font-bold text-gray-700">详细地址</label>
      <Input id="address" v-model="form.address" placeholder="请输入" />
    </div>
    <Button @click="submitOrder" class="w-full bg-blue-500 text-white">提交</Button>
  </div>
</template>

<style scoped>
/* Add any additional styles here */
</style>