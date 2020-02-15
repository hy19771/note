##AJAX
	function ajax(params) {
        let param = Object.assign({
            method: 'get',
            success(res) {
                console.info(res);
            },
            fail(res) {
                console.info(res);
            },
            data: null
        }, params), xhr = new XMLHttpRequest();

        xhr.onload = (res) => {
            if (xhr.status === 200) {
                param.success();
            } else if (xhr.status === 404) {
                layer.msg('url地址错误')
            } else {
                param.fail();
            }
        };

        xhr.open(param.method, param.url);

        if (param.data) {
            xhr.setRequestHeader('content-type', "application/x-www-form-urlencoded");
        }

        xhr.send(param.data);

    }

###AJAX调用
	ajax({
       url: api.update,
       method: 'post',
       success: function () {
          layer.close(num);
          table.reload('reload', {
             page: {
                curr: 1 //重新从第一页开始
             }
          });
        },
        data: format(Object.assign({ 
           userId: res.data.userId,
           username: res.data.username,
           tell: res.data.tell,
           avatar: res.data.avatar
        }, form.val('form')))
    });

###form-data格式化数据方法
	function format(param) {
        let str = '';
        for (let i in param) {
            str += '&' + i + '=' + param[i]
        }
        return str.slice(1);
    }