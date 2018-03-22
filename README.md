# 登录注册页
通过jQuery + bootstrap 搭建的用户登录注册页及用户信息页的展示
<br/>
代码逻辑展示<br/>

    $('#login').on('click', function() {
        var curname = $('#inputEmail3').val();
        var curpassword = $('inputPassword3').val();

        if (curname && curpassword) {
            $.ajax({
                url: '',
                type: 'POST',
                data: {
                    name: curname,
                    password: curpassword
                },
                success: function(datas) {
                    if (datas.xx == xx) {
                        //登录成功 跳转到用户信息页
                        window.location.href = ''
                    } else if (datas.xx == xx) {
                        //提示用户不存在 请注册
                    } else {
                        //提示用户密码错误 请重新输入
                    }
                },
                error: function(err) {
                    console.log(err)
                }

            })
        }

    })

    //注册
    $('#login').on('click', function() {
        var curname = $('#inputEmail3').val();
        var curpassword = $('inputPassword3').val();

        if (curname && curpassword) {
            $.ajax({
                url: '',
                type: 'POST',
                data: {
                    name: curname,
                    password: curpassword
                },
                success: function(datas) {
                    if (datas.xx == xx) {
                        //提示用户注册成功
                    } else {
                        //提示该用户已被注册
                    }
                },
                error: function(err) {
                    console.log(err)
                }
            })
        }

    })
    //页面加载完之前 发送ajax请求 请求所有用户数据 通过forEach遍历加模板字符串拼接后渲染到页面上
    document.ready(function() {
        $.ajax({
            url: '',
            type: 'GET',
            success: function(data) {
                var datas = data.results
                datas.forEach((ele, index) => {
                    $('<div></div').html(`<p><span>${ele.name}</span><span>${ele.password}</span></p>`).appendTo($('.curinfo'));

                })
            },
            error: function(err) {
                console.log(err)
            }
        })
    })

    //用户退出路由跳转
    $('.logout').on('click', function() {
        $.ajax({
            url: '',
            type: 'GET',
            success: function() {
                if (data.xx == xx) {
                    //退出成功
                }
            },
            error: function(err) {
                console.log(err)
            }
        })
    })
