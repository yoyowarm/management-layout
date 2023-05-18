<template>
	<el-menu
		default-active="1"
		class="el-menu-vertical-demo"
		@open="handleOpen"
		@close="handleClose"
		:collapse="isCollapse">
		<el-menu-item index="2">
			<img :src="homeIcon"/>
			<span class="menu-title">Home General</span>
		</el-menu-item>
		<el-submenu index="1">
			<template slot="title">
				<img :src="cartIcon"/>
				<span class="menu-title">Marketing &  Sales</span>
			</template>
			<el-menu-item index="1-1" >
				<span class="menu-title">Option_1</span>
			</el-menu-item>
			<el-submenu index="1-4">
					<template slot="title">
						<span class="menu-title">Option_2</span>
					</template>
					<el-menu-item index="1-2-1">
						<span class="menu-title">Suboption_1</span>
					</el-menu-item>
					<el-menu-item index="1-2-2">
						<span class="menu-title">Suboption_2</span>
						</el-menu-item>
					<el-menu-item index="1-2-3">
						<span class="menu-title">Suboption_3</span>
					</el-menu-item>
				</el-submenu>
				<el-menu-item index="1-3"><span class="menu-title">Option_3</span></el-menu-item>
		</el-submenu>
		<el-menu-item index="2">
			<img :src="globalIcon"/>
			<span class="menu-title">Customer Service & Operation</span>
		</el-menu-item>
		<el-menu-item index="3">
			<img :src="truckIcon"/>
			<span class="menu-title">Carrier Management</span>
		</el-menu-item>
		<el-menu-item index="4">
			<img :src="computerIcon"/>
			<span class="menu-title">Finance & Accounting</span>
		</el-menu-item>
		<el-menu-item index="5">
				<img :src="memberIcon"/>
				<span class="menu-title">HR Development & Organization Setup</span>
			</el-menu-item>
	</el-menu>
</template>

<script>
import homeIcon from '../assets/icon/home.svg'
import cartIcon from '../assets/icon/cart.svg'
import globalIcon from '../assets/icon/global.svg'
import truckIcon from '../assets/icon/truck.svg'
import computerIcon from '../assets/icon/computer.svg'
import memberIcon from '../assets/icon/member.svg'
export default {
	props: {
		isCollapse: {
			type: Boolean,
			default: false
		}
	},
	data() {
		return {
			homeIcon,
			cartIcon,
			globalIcon,
			truckIcon,
			computerIcon,
			memberIcon
		}
	},
	methods: {
		handleOpen(key, keyPath) {
			console.log(key, keyPath);
		},
		handleClose(key, keyPath) {
			console.log(key, keyPath);
		}
	}
}
</script>

<style scoped>
.el-menu-vertical-demo {
	max-width: 294px;
	background-color: #F5F5F5;
	border-right: 0px;
	color: #11263C;
}
.el-menu-vertical-demo .menu-title  {
	font-size: 16px;
	font-weight: 600;
	margin-left: 20px
}
.el-menu-vertical-demo /deep/ .el-menu {
	background-color: #F5F5F5;
}

.el-menu-vertical-demo /deep/ .el-submenu__title:hover {
	background-color: #D8DDEB;
}
/deep/ .el-submenu__title {
	display: flex;
	align-items: center;
	white-space: inherit
}
/deep/ .el-menu-item {
	display: flex;
	align-items: center;
	white-space: inherit;
	line-height: normal
}
/deep/ .el-menu-item:focus, /deep/ .el-menu-item:hover {
	background-color: #D8DDEB;
}
/deep/ .el-menu-item.is-active {
	color: #11263C;
}

</style>