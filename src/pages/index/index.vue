<!-- <template>
  <view class="index">
    <nut-button type="primary" @click="onClick">按钮</nut-button>
    <nut-toast v-model:visible="show" msg="你成功了" />
  </view>
</template>

<script setup>
import { ref } from 'vue'
const show = ref(false)
const onClick = () => {
  show.value = true
}
</script> -->
<template>
  <view>
    <!-- 预约时间段的写法 -->
    <TimesPiker @change="getTime" :isMultiple="true" :timeInterval="1" :isQuantum="true" :disableTimeSlot="disableTimeSlot">
    </TimesPiker>
    <!-- 多选时间的配置 -->
    <!-- <times @change="getTime" :timeInterval="1" :appointTime="appointTime"
		:isMultiple="true" :disableTimeSlot = "disableTimeSlot"></times> -->

    <!-- 单选的配置 -->
    <!-- <times @change="getTime" :timeInterval="1" :appointTime="appointTime"
		:isMultiple="false" :disableTimeSlot = "disableTimeSlot"></times> -->

    <!-- 预约时间段 -->
    <!-- <times @change="getTime" :timeInterval="1" :appointTime="appointTime"
		:isSection="true" :disableTimeSlot = "disableTimeSlot"></times> -->
  </view>
</template>

<script >
import TimesPiker from '@/components/pretty-times/pretty-times.vue'

export default {
	components: {
		TimesPiker
	},
	data() {
		return {
			appointTime: ["2022-02-10 15:30:00"],
			disableTimeSlot: [
				["2022-10-17 09:00:00", "2022-10-17 10:00:00"],
				["2022-05-05 16:30:00", "2022-05-05 18:30:00"]
			]
		}
	},
	methods: {
		getTime(e) {
			console.log(e)
		}
	}
}
</script>

<style>

</style>
