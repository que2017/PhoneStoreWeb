<template>
	<div>
    <van-card price="1899.00" title="P40 pro" desc="地表最强拍照" thumb="../assets/logo.png">
		<template #tags>
			<van-tag plain type="danger">标签1</van-tag>
			<van-tag plain type="danger">标签2</van-tag>
		</template>
		<template #footer>
			<van-button size="mini" @click="buyPhone">购买</van-button>
		</template>
	</van-card>
	<van-sku
		v-model="showSku"
		:sku="sku"
		:goods="goods"
		:goods-id="1"
		:quota="10"
		:hide-stock="false"
		@buy-clicked="onBuyClicked"
	/>
	</div>
</template>

<script>
export default {
	props: {
		details: Object
	},
	data () {
		return {
			showSku: false,
			sku: {
			  // 所有sku规格类目与其值的从属关系，比如商品有颜色和尺码两大类规格，颜色下面又有红色和蓝色两个规格值。
			  // 可以理解为一个商品可以有多个规格类目，一个规格类目下可以有多个规格值。
			  tree: [
			    {
			      k: '颜色', // skuKeyName：规格类目名称
			      k_s: 's1', // skuKeyStr：sku 组合列表（下方 list）中当前类目对应的 key 值，value 值会是从属于当前类目的一个规格值 id
			      v: [
			        {
			          id: '1', // skuValueId：规格值 id
			          name: '红色', // skuValueName：规格值名称
			          imgUrl: 'https://img.yzcdn.cn/1.jpg', // 规格类目图片，只有第一个规格类目可以定义图片
			          previewImgUrl: 'https://img.yzcdn.cn/1p.jpg', // 用于预览显示的规格类目图片
			        },
			        {
			          id: '2',
			          name: '蓝色',
			          imgUrl: 'https://img.yzcdn.cn/2.jpg',
			          previewImgUrl: 'https://img.yzcdn.cn/2p.jpg',
			        }
			      ],
			      largeImageMode: false //  是否展示大图模式
			    }
			  ],
			  // 所有 sku 的组合列表，比如红色、M 码为一个 sku 组合，红色、S 码为另一个组合
			  list: [
			    {
			      id: 2259, // skuId
			      s1: '1', // 规格类目 k_s 为 s1 的对应规格值 id
			      price: 100, // 价格（单位分）
			      stock_num: 110 // 当前 sku 组合对应的库存
			    },
				{
				  id: 2260, // skuId
				  s1: '2', // 规格类目 k_s 为 s1 的对应规格值 id
				  price: 100, // 价格（单位分）
				  stock_num: 110 // 当前 sku 组合对应的库存
				}
			  ],
			  price: '1.00', // 默认价格（单位元）
			  stock_num: 227, // 商品总库存
			  collection_id: 2261, // 无规格商品 skuId 取 collection_id，否则取所选 sku 组合对应的 id
			  none_sku: false, // 是否无规格商品
			  hide_stock: false // 是否隐藏剩余库存
			},
			goods: {
			  // 默认商品 sku 缩略图
			  picture: 'https://img.yzcdn.cn/1.jpg'
			}
		} 
	},
	methods: {
		buyPhone() {
			this.showSku = true;
		},
		onBuyClicked() {
			
		}
	}
} 
</script>

<style lang="stylus" rel="stylesheet/stylus">
</style>
