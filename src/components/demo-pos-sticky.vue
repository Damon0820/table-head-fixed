<template>
  <div class="table">
		<!-- 表头 -->
		<div class="table-top">
			<div class="table-top-left">
				班级\课程
			</div>
			<div class="table-top-right">
				<ul :style="{transform: `translateX(${-scrollLeft}px)`}">
					<li v-for="(item, i) in courseList" :key="i">{{item.name}}</li>
				</ul>
			</div>
		</div>

		<div class="table-bottom" @scroll="onScroll">
			<!-- 左边固定列 -->
			<div class="table-bottom-left">
				<ul>
					<li v-for="(item, i) in classList" :key="i">{{item.name}}</li>
				</ul>
			</div>
			<!-- 可编辑表格 -->
			<div class="table-main">
				<ul v-for="(courseAll, i) in editList" :key="i">
					<li v-for="(cell, j) in courseAll" :key="j">
						{{cell.className}}
						{{cell.courseName}}
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
import {courseList, classList} from './mock.js'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
	},
	data () {
		return {
			courseList,
			classList,
			scrollLeft: 0,
			scrollTop: 0,
		}
	},
	computed: {
		// 根据表头和表列生成可编辑表格
		editList () {
			let editList = []
			editList = courseList.map(course => {
				return classList.map(varClass => {
					return {
						courseId: course.id,
						courseName: course.name,
						classId: varClass.id,
						className: varClass.name,
					}
				})
			})
			return editList
		}
	},
	methods: {
		onScroll (e) {
			let {scrollTop, scrollLeft} = e.target
			this.scrollLeft = scrollLeft
		},
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
@headWidth: 134px;
@headHeight: 50px;
@cellWidth: 90px;
@cellHeight: 50px;

li, .table-top-left {
	display: flex;
	justify-content: center;
	align-items: center;
}

.table {
	width: 1000px;
	height: 600px;
	display: flex;
	flex-direction: column;
	.table-top {
		display: flex;
		.table-top-left {
			width: @headWidth;
			min-width: @headWidth;
			height: @headHeight;
			background: #ccc;
		}
		.table-top-right {
			overflow: hidden;
			>ul {
				display: flex;
				>li {
					width: @cellWidth;
					min-width: @cellWidth;
					height: @headHeight;
					background: #f99;
				}
			}
		}
	}
	.table-bottom {
		flex: 1;
		overflow: auto;
		display: flex;
		position: relative;
		.table-bottom-left {
			position: sticky;
			left: 0;
			top: 0;
			height: fit-content;
			>ul {
				>li {
					width: @headWidth;
					height: @cellHeight;
					background: #9f9;
				}
			}
		}
		.table-main {
			display: flex;
			>ul {
				>li {
					width: @cellWidth;
					height: @cellHeight;
					font-size: 12px;
				}
			}
		}
	}
}
</style>
