# 安装和使用Sass

## 安装ruby
1. 安装ruby所需环境
	<blockquote>
		#yum install gcc-c++ patch readline readline-devel zlib zlib-devel
		#yum install libyaml-devel libffi-devel openssl-devel make
		#yum install bzip2 autoconf automake libtool bison iconv-devel sqlite-devel
	</blockquote>

2. 安装RVM管理器
	<blockquote>
		#curl -L get.rvm.io | bash -s stable
	</blockquote>
3. 设置RVM环境
	<blockquote>
		#source /etc/profile.d/rvm.sh
	</blockquote>

4. 安装ruby
	<blockquote>
		#rvm install 2.1.8
	</blockquote>

5. 设置默认使用ruby的版本
	<blockquote>
		#rvm use 2.1.8 --default
	</blockquote>
6. 查看是否设置成功
	<blockquote>
		#ruby --version
	</blockquote>
7. 安装sass
	<blockquote>
		#gem install sass
	</blockquote>
8. 查看是否安装成功
	<blockquote>
		#sass -v       
	</blockquote>
9. 创建scss，编译
	<blockquote>
		#sass input.scss output.css
	</blockquote>

10. 全局监控sass文件的改变
	<blockquote>
		#sass --watch app/sass:public/stylesheets
	</blockquote>

## Sass核心语法
1. 变量
	<blockquote>
		$font-stack:    Helvetica, sans-serif;
		$primary-color: #333;

		body {
  			font: 100% $font-stack;
 		 	color: $primary-color;
			}
	</blockquote>

2. 嵌套
	<blockquote>
		nav {
  			ul {
    				margin: 0;
    				padding: 0;
    				list-style: none;
  				}

  			li { display: inline-block; }

  			a {
    				display: block;
    				padding: 6px 12px;
    				text-decoration: none;
  			}
		}
	</blockquote>

3. 引入其他Scss文件
	<blockquote>
		//reset.scss
		html,body,ul,ol{ padding:0; margin:0; }

		//base.scss
		@import 'reset.scss';
		body{
			background-color:#efefef;			
			}
	</blockquote>

4. 定义函数
	<blockquote>
		@mixin border-radius($radius) {
 			  -webkit-border-radius: $radius;
   			  -moz-border-radius: $radius;
      			  -ms-border-radius: $radius;
          		  border-radius: $radius;
			}

		.box { @include border-radius(10px); }
	</blockquote>

5. 不同选择器之间共享样式--@extend
	<blockquote>
		.message {
  			border: 1px solid #ccc;
  			padding: 10px;
 			 color: #333;
		}

		.success {
 			 @extend .message;
  			 border-color: green;
			}

		.error {
 			 @extend .message;
 			 border-color: red;
			}

		.warning {
  			@extend .message;
 			 border-color: yellow;
			}
	</blockquote>

6. 算术运算操作---aside & article
	<blockquote>
		.container { width: 100%; }


		article[role="main"] {
  			float: left;
  			width: 600px / 960px * 100%;
		}

		aside[role="complementary"] {
  			float: right;
 			 width: 300px / 960px * 100%;
		}
	</blockquote>
	
	


	
