<template>
  <div class="table">
		<table>
			<thead>
				<tr>
					<th>chapter 1</th>
					<th>chapter 2</th>
					<th>chapter 3</th>
					<th>chapter 4</th>
					<th>chapter 5</th>
					<th>chapter 6</th>
					<th>chapter 7</th>
					<th>chapter 8</th>
					<th>chapter 9</th>
					<th>chapter 10</th>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td>Sad</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
				</tr>
				<tr>
					<td>Sad</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
				</tr>
				<tr>
					<td>Sad</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
				</tr>
				<tr>
					<td>Sad</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
				</tr>
				<tr>
					<td>Sad</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
				</tr>
				<tr>
					<td>Sad</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
				</tr>
				<tr>
					<td>Sad</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
					<td>Happy</td>
				</tr>
			</tbody>
		</table>
	</div>
</template>

<script>
import {courseList, classList} from './mock.js'
export default {
  name: 'stickyTable',
	methods: {
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less" scoped>


* {
  // box-sizing: border-box;
}

body {
  margin: 10px;
}

div {
  height: 206px;
  max-width: 100vw;
  overflow-x: auto;
  overflow-y: auto;
  position: relative;
  margin-top: 100px;
}

table {
  border-collapse: collapse;
  color: lightgrey;
  table-layout: fixed;
}

thead {
  // thead and tr don't currently support sticky
  // position: -webkit-sticky;
  // position: sticky;
  // left: 0; top: 0;
  
  th {
    position: -webkit-sticky; // for safari
    position: sticky;
    top: 0; left: 0;
    
    
    &:first-child {
      z-index: 3;
    }
  }
}

th, td {
  padding: 10px 100px;
  text-transform: capitalize;
}

th {
  background: black;
  color: white;
  white-space: nowrap;
}

tr {
  background: hsl(0, 0%, 20%);
  
  &:nth-child(even) {
    background: hsl(0, 0%, 15%);
  }
  
  &:not(:last-of-type) {
    border-bottom: 2px solid rgba(yellow, 0.25);
  }
}

th, td {
  &:first-child {
    position: -webkit-sticky; // for safari
    position: sticky;
    left: 0px;
    // top: 0px; -> doesn't work in Safari 11
    /*
      thanks to https://github.com/jonjohnjohnson
      explanation: https://github.com/w3c/csswg-drafts/issues/865 
    */
    z-index: 2;
    width: 200px;
	}
}
  
td:first-child {
  tr:nth-child(odd) & {
    background: hsl(0, 0%, 20%);
    box-shadow: inset -2px 0px rgba(black, 0.25);
  }

  tr:nth-child(even) & {
    background: hsl(0, 0%, 15%);
    box-shadow: inset -2px 0px rgba(black, 0.25);
  }
}

</style>
