
<!DOCTYPE html>
<html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <title style='text-align: center'>浙江大学通行码</title>
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <link rel="stylesheet" href="main.css"></link>
    <!-- <link rel="text/javascript" href="{% static 'jquery.qrcode.min.js' %}"> -->
    
    <script type="text/javascript" src="jquery-1.7.2.min.js"></script>
    <script type="text/javascript" src="jquery.qrcode.min.js"></script>
    <script>setTimeout("location=location; ", (24*3600*1000)*3); </script>

<script>
    jQuery(function(){

        var colour = '1E90FF';
        var flag = '';
        if(null == colour || "" == colour){
            colour = "CCCCCC";
        }


        var mzt='';
        var dateTime='';
        // var array=getJkm();
        var array=[1,2];
        if(array.length>0){
            // mzt = array[0].mzt;
            mzt='green';
            // dateTime = array[0].dateTime;
            dataTime='123';
        }
        
        if(mzt!='green'){
            colour = "CCCCCC";
        }
        if(mzt=='green'){
            // $("#hzjkm").append('<div  class="hz" style="color: #55b957">健康码为 绿码</div>');
        }
        if(mzt=='yellow'){
            $("#hzjkm").append('<div  class="hz" style="color: #ee8232">健康码为 黄码</div>');
        }
        if(mzt=='red'){
            $("#hzjkm").append('<div class="hz" style="color: #e8453b">健康码为 红码</div>');
        }

        if(mzt=='orange'){
            $("#hzjkm").append('<div class="hz" style="color: #FFA500">健康码为 橙码</div>');
        }
        if(mzt==''){
            colour = "1E90FF";
            $("#hzjkm").append('<div class="hz" style="color: #006bc7">健康码获取失败（请打开支付宝出示）</div>');
        }
        if(mzt=='' && flag== 'Invalid'){
            colour = "CCCCCC";
        }
        if(dateTime!=''){
            $("#dateTime").append('<div class="time">同步时间：'+dateTime+'</div>');
        }

        // 已删除
        if(''  == '1'){
            colour='CCCCCC';
        }
        // 核酸检测为是
        if('否'  == '是'){
            colour='EB6E18';
        }

        jQuery('#output').qrcode({
            render: "canvas",
            width: 180,
            height: 180,
            foreground: "#"+colour,
            background: "#FFF",
            text:"此二维码真实有效，与浙大钉中的二维码具有同等效力，请予以放行。"
            // text:"大不自多 海纳江河 惟学无际 际于天地 形而上学 不行退学"
            // text: "da bu zi duo hai na jiang he weixuewujijiyutiandixingshangweidaoxi"
        });
    });


    if(true){
        //获取系统时间
        function showTime() {
            nowtime = new Date();
            year = nowtime.getFullYear();//年
            month = nowtime.getMonth() + 1;//月
            day = nowtime.getDate();//日
            hour = nowtime.getHours();//时
            minutes = nowtime.getMinutes(); //分
            seconds = nowtime.getSeconds(); //秒
            //文字增加空格
            document.getElementById("div_timer").style = "white-space:pre;";
            //显示时间
            document.getElementById("div_timer").innerText = p(month) + "月" + p(day) + "日 " + p(hour) + ":" + p(minutes) + ":" + p(seconds);
            document.getElementById('youxiao').innerText="有效期：2020-"+p(month)+"-"+p(day)+" - 2020-"+p(month)+"-"+p(day);
            document.getElementById('tb').innerText="同步时间：2020-"+p(month)+"-"+p(day)+" 09:03:26";
        }
        setInterval("showTime()", 1000);
        //月日时分秒小于10补0
        function p(s) {
            return s < 10 ? '0' + s : s;
        }
    }

</script>
<script>
    function gen(){
        document.getElementById('btn').style.display="none";
        var name=document.getElementById('userinput').value;
        document.getElementById('username').innerText=name+'的通行码'
        document.getElementById('userinput').style.display="none";
    }

</script>

</head>










<body class="blue-bg" data-gr-c-s-loaded="true">
<div class="banner"><img src="text.png"></div>




<div class="content-box">
    <div class="top-title">
        <h3 id='username'></h3>
        

            <span class="bgr-blue">研究生</span>
            

        


    </div>
    
        <strong><div class="time2" id="div_timer" style="white-space: pre;"></div></strong>
    
    <div class="qr">
        
            <div id="output" style="margin-top: 10px;margin-bottom: 10px"></div>
        
        
        
        
        
    </div>
    
        
            <div class="time" id='youxiao'>有效期：2020-05-24 - 2020-05-24</div>
        
<div style="text-align: center;">
<input id='userinput' placeholder="输入名字，点击后面的按钮"></input>
<button id='btn' onclick="gen()">生成</button>
</div>

    <div id="hzjkm"><div class="hz" style="color: #55b957">健康码为 绿码</div></div>


    <div id="dateTime"><div class="time" id="tb">同步时间：2020-05-24 09:03:26</div></div>
    
        <p class="tip" style="margin-top: 10px;">凭蓝码可在浙江大学校园内通行<br>请主动出示，配合检查</p>
    
    
    <div style="text-align:center; margin-top: 10px">
        <a target="_blank" href="http://one.zju.edu.cn/taskcenter/wechat/index">办事大厅</a>&nbsp;&nbsp;&nbsp;
        <a target="_blank" href="http://one.zju.edu.cn/pass_code/zx/getList">申请记录</a>&nbsp;&nbsp;&nbsp;





    </div>
</div>
<div class="bottom-tip">
    <h3>安 保 处 ：0571-88206110</h3>
    <a href="http://xwfw.zju.edu.cn/mobile/redir.php?catalog_id=371039" target="_blank" class="link-btn">常见问题</a>
    <h3>技术支持：0571-87951669</h3>
</div>



</body></html>
