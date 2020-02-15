#Layui

#css

##引入
	<link src='layui/css/layui.css'>
	样式都是用class控制

###按钮
	<button class='layui-btn layui-btn-primary layui-btn-xs'></button>
	控制按钮大小
	xs 迷你
	sm 小按钮
	什么都不写就是默认按钮
	lg 大型按钮
	fluid 流体按钮,占盒子整个宽	
	
	按钮组
	<div class="layui-btn-group">
    	<button type="button" class="layui-btn">增加</button>
    	<button type="button" class="layui-btn ">编辑</button>
    	<button type="button" class="layui-btn">删除</button>
	</div>

###input文本框
	<input type="text" name="title" required  lay-verify="required" placeholder="请输入标题" autocomplete="off" class="layui-input">
	
	lay-verify 用于表单验证
	
###单选框
	 <input type="radio" name="sex" value="男" title="男" checked="">

###复选框
	<div class="layui-input-block">
      <input type="checkbox" name="like[write]" title="写作">
      <input type="checkbox" name="like[read]" title="阅读">
      <input type="checkbox" name="like[daze]" title="发呆">
    </div>


#js

##引入区别
####引入layui.all.js
	<script src='layui.all.js'></script>
	<script>
		//可以直接使用
		let table = layui.table,
			form = layui.form,
			$ = layui.jquery,
			layer = layui.layer;
	
	</script>

	<script src='layui.js'></script>
	<script>
		// 必须使用layui.use
		layui.use('table','form','jquery','layer',function(){
			let table = layui.table,
			form = layui.form,
			$ = layui.jquery,
			layer = layui.layer;
		{
	</script>

##table

	<table lay-filter="tableEle" id="table"></table>

####table渲染
	table.render({
        //table绑定的id
        elem: '#table',
        // 获取数据的地址
        url: api.list,
        id: 'reload',
        // table表头设置
        cols: [[
            {title: '序号', type: 'numbers'},
            {field: 'name', title: '姓名'},
            {
                field: 'sex', title: '性别', templet: function (d) {
                    return d.sex === '0' ? '男' : '女';
                }
            },
            {field: 'age', title: '年龄'},
            {field: 'address', title: '地址'},
            {field: 'school', title: '学校'},
            {title: '操作', toolbar: '#tool'}
        ]],
        // table渲染完成事件
        done(res) {
            // console.info(res)
        },
        // 设置请求参数
        request: {
            'pageName': 'start'
        },
        page: true,
        limit: 5,
        limits: [5, 10],
        parseData(res) {
            return {
                code: 0,
                count: res.data.totalRow,
                data: res.data.list
            }
        }
    });

####table事件绑定
	table.on('tool(tableEle)', function (res) {
        if (res.event === 'edit') {
            
        } else if (res.event === 'del') {
        }
    });

##弹出层
	let num = layer.open({
                title: '用户信息',
                type: 1,
                area: ['300px', '400px'],
                content: $('#formEle'),
                btn: ['确认', '取消'],
                msg: '点击',
                success: function () {
					// 成功弹出后,表单赋值,没有第二个参数就是获取值
                    form.val('form', res.data);
                },
                yes: function () {
                    //第一个按钮
                    
                },
                btn2: function (res) {
                    //第二个按钮
       
                },
            });