<template>
    <van-tabs v-model="active">
		<van-tab title="华为">
			<PhoneCard></PhoneCard>
		</van-tab>
		<van-tab title="荣耀">荣耀手机</van-tab>
		<van-tab title="小米">小米手机</van-tab>
		<van-tab title="苹果">苹果手机</van-tab>
		<van-tab title="OPPO">oppo手机</van-tab>
		<van-tab title="VIVO">vivo手机</van-tab>
	</van-tabs>
</template>

<script>
import PhoneCard from './PhoneCard.vue'

export default {
	data () {
		return {
			active: 0
		} 
	},
	methods: {
		
	},
	components: {
		PhoneCard
	}
} 
</script>

<style lang="stylus" rel="stylesheet/stylus">
</style>
