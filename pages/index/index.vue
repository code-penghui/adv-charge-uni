<template>
	<view>
		<view class="page-header padding-6-10">
			<u-row gutter="16">
				<u-col span="11">
					<u-search placeholder="输入目的地/电站名" :show-action="false" :disabled="true" @click="onSearchClick()">
					</u-search>
				</u-col>
				<u-col span="1">
					<u-icon name="account-fill" size="50" color="#999999" @click="onAccountClick()"></u-icon>
				</u-col>
			</u-row>
		</view>
		<view class="page-body">
			<map class="map" :latitude="location.latitude" :longitude="location.longitude" :controls="location.controls"
				:show-location="true"></map>
		</view>
		<u-toast ref="uToast" />
	</view>
</template>

<script>
	export default {
		data() {
			return {
				location: {
					latitude: 39.923949,
					longitude: 116.518281,
					markers: [{}],
					controls: [{
						id: 20001,
						iconPath: '/static/icon/currect-location.png',
						position: {
							top: 100,
							left: 180,
							width: 42,
							height: 42
						}
					}]
				}
			}
		},
		onLoad() {

		},
		methods: {
			/**
			 * 账户按钮点击事件
			 */
			onAccountClick() {
				this.$refs.uToast.show({
					title: '账户中心',
					type: 'success'
				})
			},

			/**
			 * 搜索框点击事件
			 */
			onSearchClick() {
				this.$refs.uToast.show({
					title: '搜索',
					type: 'success'
				})
			}
		}
	}
</script>

<style lang="scss">
	.map {
		height: 100%;
		width: 100%;
	}
</style>
