<template lang="html">
	<div class="page">
		<header>
			<mt-header title="首页">
				<router-link to="/" slot="left">
					<mt-button icon="back">全国</mt-button>
				</router-link>
				<mt-button icon="more" slot="right"></mt-button>
			</mt-header>
		</header>
		<section class="swipe">
			<mt-swipe :defaultIndex="1" :auto="0">
				<mt-swipe-item v-for="(s,i) in swipeList" :key="i">
					<img class="page-lazyload-image" :src="s.src"/>
				</mt-swipe-item>
			</mt-swipe>
		</section>
		<section class="nav">
			<div>
				<div class="weui-flex nav__tabs">
					<div class="weui-flex__item" v-for="item in navList">
						<div class="weui-grid__icon">
							<img :src="item.src" alt="">
						</div>
						<p class="weui-grid__label">{{item.text}}</p>
					</div>
				</div>
			</div>
		</section>
		<section class="navbar">
			<div class="navbar-header">
				<mt-navbar v-model="selected">
					<mt-tab-item :id="n.id" v-for="n in navbar" :key="n.id">{{n.text}}</mt-tab-item>
				</mt-navbar>
			</div>
			<!-- tab-container -->
			<div class="navbar-tab">
				<mt-tab-container v-model="selected" :swipeable="false">
					<mt-tab-container-item :id="navTab.id">
						<div class="weui-panel weui-panel_access">
							<div class="weui-panel__bd">
								<a v-for="(item,i) in navTab.list" :key="i" href="javascript:void(0);" class="weui-media-box weui-media-box_appmsg">
									<div class="weui-media-box__hd">
										<img class="weui-media-box__thumb"
											 src="http://fuss10.elemecdn.com/b/18/0678e57cb1b226c04888e7f244c20jpeg.jpeg"
											 alt="">
									</div>
									<div class="weui-media-box__bd">
										<div>
											<span class="tab-item__title">{{item.name}}</span>
										</div>
										<div>
											<span class="tab-item__des">{{item.des}}</span>
										</div>
										<div>
											<i class="icon-clock-o"></i>
											<span class="tab-item__des">{{item.time}}分钟</span>
											<i class="icon-thumbs-o-up"></i>
											<span class="tab-item__des">{{item.recommend}}人推荐</span>
										</div>
										<div>
											<span class="tab-item__red-badge">上门</span>
											<span class="tab-item__green-badge">到店</span>
											<span>￥<font class="tab-item__price">{{item.price}}</font> </span>
											<span class="tab-item__oldprice">￥<font
													class="tab-item__des">{{item.oldprice}}</font></span>
										</div>
									</div>
								</a>
							</div>
						</div>
					</mt-tab-container-item>
				</mt-tab-container>
			</div>
		</section>
		<footer>

		</footer>
	</div>
</template>

<script>
	export default {
		data(){
			return {
				selected: '1',
				swipeList: [
					{
						src: 'http://fuss10.elemecdn.com/b/18/0678e57cb1b226c04888e7f244c20jpeg.jpeg'
					}, {
						src: 'http://fuss10.elemecdn.com/3/1e/42634e29812e6594c98a89e922c60jpeg.jpeg'
					}, {
						src: 'http://fuss10.elemecdn.com/1/c5/95c37272d3e554317dcec1e17a9f5jpeg.jpeg'
					}],
				navList: [
					{
						src: 'http://fuss10.elemecdn.com/b/18/0678e57cb1b226c04888e7f244c20jpeg.jpeg',
						text: '我要预约'
					}, {
						src: 'http://ico.58pic.com/iconset01/QQ-Badge-Museum/gif/87490.gif',
						text: '优惠充值'
					}, {
						src: 'http://ico.58pic.com/iconset01/QQ-Badge-Museum/gif/87486.gif',
						text: '优惠充值'
					}, {
						src: 'http://ico.58pic.com/iconset01/QQ-Badge-Museum/gif/87513.gif',
						text: '优惠充值'
					}],
				navbar: [
					{
						id: '1',
						text: '全部'
					}, {
						id: '2',
						text: '兔拼团'
					}, {
						id: '3',
						text: '胸部'
					}, {
						id: '4',
						text: '臀部'
					}, {
						id: '5',
						text: '颈部'
					}, {
						id: '6',
						text: '全身'
					}],
				navTab: {
					id: '1',
					list:[{
						name:'招牌小菜',
						des:'微辣、热门小菜',
						time:'60',
						recommend:'14',
						price:'299',
						oldprice:'358'
					},{
						name:'招牌小菜',
						des:'微辣、热门小菜',
						time:'60',
						recommend:'14',
						price:'299',
						oldprice:'358'
					},{
						name:'招牌小菜',
						des:'微辣、热门小菜',
						time:'60',
						recommend:'14',
						price:'299',
						oldprice:'358'
					}]
				}
			}
		},
		watch: {
			selected(val){
				console.log(val);
			}
		}
	}
</script>

<style lang="less" rel="stylesheet/less" scoped>
	.page {
		height: 100%;
		background-color: #E2E2E2;
		overflow-y: scroll;

		.swipe {
			height: 20vh;

			.page-lazyload-image {
				width: 100%;
				margin: 0 auto;
				margin-bottom: 10px;
				background-color: #DDD;
			}

		}

		.nav {
			.nav__tabs {
				background-color: #FFF;
				padding: .6rem;
			}
			.weui-flex {
				.weui-flex__item {
					.weui-grid__icon {
						width: 3rem;
						height: 3rem;

						img {
							border-radius: 100%;
						}

					}
				}
			}
		}

		.navbar {
			margin-top: .6rem;

			.navbar-header {
				overflow-y: scroll;
			}
			.mint-navbar {
				width: 500px;
				padding-bottom: 2px;
			}
			.navbar-tab {

				.weui-media-box__hd {
					width: 6rem;
					height: 7rem;
				}
				.weui-media-box__bd {
					.tab-item__title {
						font-weight: bold;
					}
					.tab-item__des {
						font-size: .9rem;
						color: #666;
					}
					.tab-item__red-badge {
						padding: 3px 10px;
						border: 1px solid #EC8B89;
						border-radius: 6px;
						font-size: .6rem;
						color: #EC8B89;
					}
					.tab-item__green-badge {
						padding: 3px 10px;
						border: 1px solid #0BB20C;
						border-radius: 6px;
						font-size: .6rem;
						color: #0BB20C;
					}
					.tab-item__price {
						color: #EC8B89;
					}
					.tab-item__oldprice {
						color: #666;
						text-decoration: line-through;
					}
				}
			}
		}

	}

	.nav-list {
		img {
			height: 10vh;
		}
	}
</style>