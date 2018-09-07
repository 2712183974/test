# test
测试效果
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title></title>
	</head>
	<body>
		
		
		<script type="text/javascript">
//			将值存储在Cookie里面
			function setCookie(name,val,time){
				var date = new Date();//获取当前时间
				date.setTime(date.getTime()+24*60*60*1000*time);//设置要存储的时间：当前时间加上要存储的时间戳；以毫秒计算
				date.toUTCString();//把时间戳转换成标准格林威治时间
				document.cookie = name+"="+val+";expires="+date.toUTCString();
			}
//			setCookie("name",2712183974);
//			setCookie("name","1480224325",2);
//			删除cookie键值
			function delCookie(name){
				var date = new Date();//获取当前时间
				date.setTime(date.getTime()-10);//设置要过期的时间：小于等于当前时间
				date.toUTCString();//把时间戳转换成标准格林威治时间
				document.cookie = name+"=;expires="+date.toUTCString();
			}
//			delCookie("name");
			
//			获取cookie里面指定的值
			function getCookie(name){
				var c = document.cookie;
				var n = c.split(";"); //将浏览器里面所有的cookie转换成数组
				for(var i = 0;i<n.length;i++){
					var a = n[i].trim();//去掉前后的空格
					var b = a.split("=");
					if(b[0] == name){
						return b[1];
					}
				}
//				防止获取的值不存在而报错
				return "";
			}
//			console.log(getCookie("qq"));
			
			function getCookie2(name){
			    var q = document.cookie;
				var w = q.split(";");
			    for(var i = 0;i<w.length;i++){
			    	console.log(w.indexOf("name"));
			    }
			}
//			getCookie2();
			
			
//			html5的localStorage与sessionStorage的本地存储
			localStorage.setItem("qq","546546856");
//			localStorage.clear();
            console.log(localStorage.getItem("qq"));
//			sessionStorage.setItem("mima","35545sdasds");
			
			
			
			//创建web SQL浏览器数据库
			var db = openDatabase('mydb', '1.0', 'Test DB', 2 * 1024 * 1024);
			db.transaction(function (tx) {
			   tx.executeSql('create table if not exists logs(id unique, log)');
			   tx.executeSql('insert into logs (id, log) values (1, "菜鸟教程")');
			   tx.executeSql('insert into logs (id, log) values (2, "www.runoob.com")');
            });
		</script>
	</body>
</html>
