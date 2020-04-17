# test6
function draw(){
	var searchform = document.getElementById("searchForm");
	var form = searchform.Form.value;

	
	var count = 0;//树个数		
	var s = form.split(/[\n][\n]/);
	//alert(s.length);
	/*for(var l=0; l<s.length; l++){
		alert(s[l]);
		}*/
	for(var i=0; i<s.length; i++){
		alert(s[i]);
		deal_form(s[i]);
		//2.处理数据
		
		if(document.getElementById('Form').value != "")
		{treeData = transData(data, 'value', 'sj', 'children');}
		//3.展示树
		drawTree(treeData,id);
		document.getElementById('Form').value = "";
		id = id + 1;
		data = [];
	}

function transData(a, idStr, pidStr, childrenStr) {
	var r = [], hash = {}, id = idStr, pid = pidStr, children = childrenStr, i = 0, j = 0, len = a.length;
	for (; i < len; i++) {
		hash[a[i][id]] = a[i];
	}
	for (; j < len; j++) {
		var aVal = a[j], hashVP = hash[aVal[pid]];
		if (hashVP) {
			!hashVP[children] && (hashVP[children] = []);
			hashVP[children].push(aVal);
		} else {
			r.push(aVal);
		}
	}
	return r;
}

function drawTree(treeData,id) {
	if(id==1)
	{var  myChart = echarts.init(document.getElementById("container1"));//div元素节点的对象
	
	myChart.setOption({
		tooltip : {
			trigger : 'item',
			triggerOn : 'mousemove'
		},
		series : [ {
			type : 'tree',
			name : 'TREE_ECHARTS',
			data : treeData,
			top : '5%',
			left : '30%',
			bottom : '5%',
			right : '15%',
			symbolSize : 20,
			label : {
				normal : {
					position : 'left',
					verticalAlign : 'middle',
					align : 'right'
				}
			},
			leaves : {
				label : {
					position : 'right',
					verticalAlign : 'middle',
					align : 'left'
				}
			},
			expandAndCollapse : true ,
			initialTreeDepth : 2  //展示层级数,默认是2
		} ]
	});
	//4.树绑定事件
	 myChart.on('click', function(params) {
		var name = params.data.name;//点击的节点的name
		var value = params.data.value;//点击的节点的value
		//调用点击事件
		clickNode(name,value);
	});
	
	}
	else if(id==2)
        {var  myChart = echarts.init(document.getElementById("container1"));//div元素节点的对象
        ...        //同id==1的情况
        }
        else if(id==3)
        {var  myChart = echarts.init(document.getElementById("container3"));//div元素节点的对象
        ...        //同id==1的情况
        }
        else if(id==4)
        {var  myChart = echarts.init(document.getElementById("container4"));//div元素节点的对象
        ...        //同id==1的情况
        }
        else if(id==5)
        {var  myChart = echarts.init(document.getElementById("container5"));//div元素节点的对象
        ...        //同id==1的情况
        }
}




<div class="container" id="myCarousel">
		<div id="carousel-example-generic" class="carousel slide" data-interval="false">
			<ol class="carousel-indicators">	//轮播导航点
				<li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
				<li data-target="#carousel-example-generic" data-slide-to="1"></li>
				<li data-target="#carousel-example-generic" data-slide-to="2"></li>
				<li data-target="#carousel-example-generic" data-slide-to="3"></li>
				<li data-target="#carousel-example-generic" data-slide-to="4"></li>
			</ol>
			<div class="carousel-inner">	//轮播内容
				<div class="item active">
					<div id="container1" style="width:800px;height:600px;"></div>
					<script type="text/javascript"src="js/echarts.min.js"></script>
					<script type="text/javascript" src="js/treeEcharts.js"></script>
				</div>
				<div class="item">
					<div id="container2" style="width:800px;height:600px;"></div>
				</div>
				<div class="item">
					<div id="container3" style="width:800px;height:600px;"></div>
				</div>
				<div class="item">
					<div id="container4" style="width:800px;height:600px;"></div>
				</div>
				<div class="item">
					<div id="container5" style="width:800px;height:600px;"></div>
				</div>
			</div>
			<a href="#carousel-example-generic" class="left carousel-control" data-slide="prev"><span class="glyphicon glyphicon-chevron-left">		//轮播切换按键
			</span></a>
			<a href="#carousel-example-generic" class="right carousel-control" data-slide="next"><span class="glyphicon glyphicon-chevron-right">									</span></a>
		</div>
