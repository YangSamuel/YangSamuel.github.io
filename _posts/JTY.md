<!DOCTYPE html>
<html>

<head>
    <title>金太阳预约</title>
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta http-equiv="Content-Type" content="textml; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=0.5, maximum-scale=2.0, user-scalable=yes" />
    <script type="text/javascript" src="js/jquery.min.js"></script>
    <script type="text/javascript" src="js/amazeui.min.js"></script>
    <link rel="stylesheet" type="text/css" href="css/amazeui.css">
    <link rel="stylesheet" type="text/css" href="css/JTY.css">
</head>

<body>
    <!-- <div style="max-width:640px;min-width:320px;margin:0 auto;position:relativ;background:url(images/beijing.png)no-repeat;padding-top: 300px;background-size:cover;">
        <div id="formbackground" style="position:absolute; z-index:-1;">
        <img src="images/beijing.png"  width="100%;display:block;" /></div>
        <script type="text/javascript">
        $(function() {
            $('#formbackground').height($(window).height());
            $('#formbackground').width($(window).width());
        });
        </script>-->
        <a href="" class="logoBox"><div style="max-width:640px;min-width:320px;margin:0 auto;position:relative">
            <img src="images/logo.png">
        </a>

    <div class="list">
        <div class="div1">
            <label>姓名：</label>
            <input type="text" name="name" placeholder="这里输入姓名" ；>
        </div>
        <div class="div1">
            <label>电话：</label>
            <input onkeyup="this.value=this.value.replace(/\D/g,'')" onafterpaste="this.value=this.value.replace(/\D/g,'')" type="text" name="name" maxlength="11" placeholder="这里输入电话" ；>
        </div>
        <div class="div1">
            <label>卡号：</label>
            <input onkeyup="value=value.replace(/[^\w\.\/]/ig,'')" type="text" name="name" placeholder="这里输入卡号" ；>
        </div>
        <div class="div1">
            <label>门店：</label>
            <select>
                <option value="volvo">科技园门店</option>
                <option value="saab">新洲店</option>
                <option value="opel">东门店</option>
                <option value="audi">福田店</option>
            </select>
        </div>
        <div class="div1">
            <label style="float:left">时间：</label>
            <!--<input style="width: 60%!important;background: none;margin:0;float:left" type="text" class="am-form-field" placeholder="请选择时间" data-am-datepicker readonly/>-->
            <div class="am-g">
                <div class="am-u-sm-6">
                    <p>
                        <input type="text" class="am-form-field" placeholder="今天之前的日期被禁用" id="my-start-2" />
                    </p>
                </div>
            </div>
        </div>
        <label>留言：</label>
        <br/>
        <div class="div2">
            <textarea placeholder="这里输入留言"></textarea>
        </div>
        <button type="button" class="am-btn am-btn-default2 am-radius">提 交</button>
    </div>
    </div>
    </div>

    <script>
    $(function() {
        var nowTemp = new Date();
        var now = new Date(nowTemp.getFullYear(), nowTemp.getMonth(), nowTemp.getDate(), 0, 0, 0, 0);
        var $myStart2 = $('#my-start-2');

        var checkin = $myStart2.datepicker({
            onRender: function(date) {
                return date.valueOf() < now.valueOf() ? 'am-disabled' : '';
            }
        }).on('changeDate.datepicker.amui', function(ev) {
            if (ev.date.valueOf() > checkout.date.valueOf()) {
                var newDate = new Date(ev.date)
                newDate.setDate(newDate.getDate() + 1);
                checkout.setValue(newDate);
            }
            checkin.close();
            $('#my-end-2')[0].focus();
        }).data('amui.datepicker');

        var checkout = $('#my-end-2').datepicker({
            onRender: function(date) {
                return date.valueOf() <= checkin.date.valueOf() ? 'am-disabled' : '';
            }
        }).on('changeDate.datepicker.amui', function(ev) {
            checkout.close();
        }).data('amui.datepicker');

    })
    </script>
</body>
