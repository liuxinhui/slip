#slip使用指南

移动端跟随手指滑动组件，零依赖。

代码
	
	此处为样式

	body{
			background: #cecece;
			width: 100%;
			height: 100%;
		}
		img{
			width: 100%
		}

	 此处为div布局

	<div id="container">
		<div class="page page-1"><img src="images/1.jpg"></div>
		<div class="page page-2"><img src="images/2.jpg"></div>
		<div class="page page-3"><img src="images/3.jpg"></div>
		<div class="page page-4"><img src="images/4.jpg"></div>
		<div class="page page-5"><img src="images/5.jpg"></div>
	</div>

	在页面下部引入slip.min.js和以下js代码

	<script type="text/javascript" src="js/slip.min.js"></script>
		<script type="text/javascript">
			var container = document.getElementById('container');
			var pages = document.querySelectorAll('.page');
			var slip = Slip(container, 'y').webapp(pages);
		</script>

注意：以下js代码是上下滑动且滑动到最后以页面不会更新也不会返回第一页面重新播放

	<script type="text/javascript">
			var container = document.getElementById('container');
			var pages = document.querySelectorAll('.page');
			var slip = Slip(container, 'y').webapp(pages);
		</script>

注意：以下js代码是可reload的（根据设定的页数循环播放的）

	<script type="text/javascript">
				Slip(document.getElementById('container'), 'x').webapp().end(function() {
		  		if (this.page === 3) location.reload();
				});
			</script>
解说：

Slip：暴露到全局的方法，只要你引入slip.js，就可以得到这个实用牛逼的方法。

container: 被滑动的容器，里面是每个滑动页面。

'y': 页面滑动的方向，你也可以传入'x'。（y为上下滑动、x为左右滑动）

webapp: 设置页面展现为全屏滑动页面的方法。

pages: 页面元素列表。