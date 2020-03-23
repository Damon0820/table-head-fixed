<template>
  <div class="table">
			待实现
			<!-- 表格行头：固定行 -->
			<!-- <div class="table-top" >
				<div class="wrap">
					<ul>
						<li v-for="(course, i) in courseList" :key="i">{{course.name}}</li>
					</ul>
				</div>
			</div>
			<div class="table-bottom"> -->
				<!-- （二维）表格 -->
				<!-- <div class="table-main">
					
				</div>
			</div> -->

			<!-- 表格列头：固定列 -->

			<!-- 表格行列共同头：left-top左上角固定 -->
			
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
			courseList, // 表格头的行
			classList, // 表格头的列
		}
	},
	computed: {
		/**
		 * 根据表格头的行和列生成（二维）表格
		 */
		cellList () {
			let cellList = []
			cellList = this.courseList.map((course, courseIndex) => {
				return this.classList.map((cla, claIndex) => {
					return {
						course,
						cla,
					}
				})
			})
			return cellList
		},
	},
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>
@headW: 90px; // 表列头宽
@headH: 50px; // 表行头高
@cellW: 90px; // 表格宽
@cellH: 50px; // 表格高

li {
	display: flex;
	justify-content: center;
	align-items: center;
}

.table {
	position: relative;
	.table-top {
		position: relative;
		left: @cellW;
		>.wrap {
			>ul {
				display: flex;
				>li {
					width: @cellW;
					height: @cellH;
				}
			}
		}
	}
}


</style>
