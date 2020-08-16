<template>
    <van-tabs v-model="active">
		<van-tab title="华为">华为手机</van-tab>
		<van-tab title="荣耀">荣耀手机</van-tab>
		<van-tab title="小米">小米手机</van-tab>
		<van-tab title="苹果">苹果手机</van-tab>
		<van-tab title="OPPO">oppo手机</van-tab>
		<van-tab title="VIVO">vivo手机</van-tab>
	</van-tabs>
</template>

<script>
export default {
	data () {
		return {
			active: 0
		} 
	},
	methods: {
		
	},
} 
</script>

<style lang="stylus" rel="stylesheet/stylus">
</style>
