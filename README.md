https://img-cdn-tx.dcloud.net.cn/stream/plugin_screens/2afce870-3618-11eb-a8f3-e1f30a5c6517_0.png/webp?&v=1607076338
```html
<template>

    <!-- 预约时间段的写法 -->
    <TimesPiker @change="getTime" :isMultiple="true" :timeInterval="1" :isQuantum="true" :disableTimeSlot="disableTimeSlot">
    </TimesPiker>
    <!-- 多选时间的配置 -->
    <!-- <TimesPiker @change="getTime" :timeInterval="1" :appointTime="appointTime"
        :isMultiple="true" :disableTimeSlot = "disableTimeSlot"></TimesPiker> -->

    <!-- 单选的配置 -->
    <!--    <TimesPiker @change="getTime" :timeInterval="1" :appointTime="appointTime"
        :isMultiple="false" :disableTimeSlot = "disableTimeSlot"></TimesPiker> -->

    <!-- 预约时间段 -->
    <!-- <TimesPiker @change="getTime" :timeInterval="1" :appointTime="appointTime"
        :isSection="true" :disableTimeSlot = "disableTimeSlot"></TimesPiker> -->

</template>
```

### 在 script 中使用
``` javascript
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
```

### 属性说明
| 属性名            | 类型    | 默认值                  | 备注                                                                                   |
|-------------------|---------|-------------------------|----------------------------------------------------------------------------------------|
| isSection         | Boolean | false                   | 是否选择时间段（将 isMultiple 置为 false）                                              |
| isMultiple        | Boolean | false                   | 是否多选                                                                               |
| disableText       | String  | 已约满                  | 禁用显示的文本                                                                         |
| undisableText     | String  | 可预约                  | 未禁用显示的文本                                                                       |
| timeInterval      | Number  | 1                       | 时间间隔，单位为小时                                                                   |
| selectedTabColor  | String  | #FB4B5C                 | 日期栏选中的字体颜色                                                                   |
| appointTime       | Array   | '2020-12-05 17:00:00'   | 被预约的具体时间                                                                       |
| beginTime         | String  | '09:00:00'              | 开始时间                                                                               |
| endTime           | String  | '19:00:00'              | 结束时间                                                                               |
| disableTimeSlot   | Array   | []                      | 禁用时间段，格式为 `[[begin_time: "2021-11-17 11:00:00", end_time: "2021-11-17 16:00:00"]]` |
| isQuantum         | Boolean | false                   | 选择两个时间点为一个时间段，效果可参考运行案例                                         |
