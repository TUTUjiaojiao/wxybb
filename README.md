# 老婆贴贴~
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>老婆贴贴~~</title>
    <link type="text/css" rel="stylesheet" href="https://web-file.20it.cn/template/yesno/css/style.css?v1.0.289">
    <meta name="viewport" content="width=500, target-densitydpi=device-dpi, user-scalable=0">
</head>
<body>
<div id="div_container">
    <div id="div_onlyyou" style="display: block; height: 1342px; background-image: url(https://web-img.20it.cn/static/images/2303/cb9d0a4910bc73e10b512fd3d3fec8da.jpg);">
        <div id="div_oy_inner" style="height: 1342px;background: rgba(255,255,255,0.80)">
            <div class="div_oy_text">
                <h1>王曦瑶我爱你~~</h1>
                <img class="img_oy_text" src="https://web-img.20it.cn/static/images/2303/9d9a24e319353fd19ee3c03037bbea3f.gif" />
                <p class="text" style="display: none;">世界并不会对你温柔以待，但我会🌈❤️💌🌷💖🌹🍬✨
遇见你，我花光了所有的运气。
爱过你，我用尽了最好的自己。
野心不大，只想做你一个人的天下。</p>
                <p class="p_oy_text"></p>
                <ul id="ul_oy_benefit">
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                    <li class="li_oy_benefit"></li>
                </ul>
            </div>
            <ul id="ul_oy_btn">
                <li onclick="oy_go_next()">Yes~&nbsp;&nbsp;❤</li>
                <li onclick="oy_show_benefit()">别点这&nbsp;&nbsp;✖</li>
            </ul>
            <div id="div_oy_note" onclick="$('#div_oy_note').hide()">
                <img src="/template/yesno/images/emoji_kelian.jpg" alt="">
                <br>
                请告诉我Yes！
                <div id="div_oy_note_close">✖</div>
            </div>
            <div id="div_oy_yes">
                <img src="/template/yesno/images/emoji_bixin.jpg" alt="">
                <br>
                太好了！哈哈~
            </div>
        </div>
    </div>
    <div class="div_btn" id="div_music" onclick="music_switch()">
        <audio id="audio_music" autoplay="autoplay" preload="auto" loop>
            <source src="https://sf6-cdn-tos.douyinstatic.com/obj/tos-cn-ve-2774/c30a9f269c7f423182a44a048373b3bd" type="audio/mpeg" />
            <embed id="main_audio_ie8" hidden="true" autostart="true" height="0" width=0 loop="true" src="https://sf6-cdn-tos.douyinstatic.com/obj/tos-cn-ve-2774/c30a9f269c7f423182a44a048373b3bd" autoplay="autoplay"/>
        </audio>
    </div>
</div>
<div class="div_btn" id="btn-make">
    <a href="https://mp.weixin.qq.com/s/zFfhCoCjyob7cYPjrtHqRQ"><span>制作</span></a>
</div>
<div class="div_btn" id='div_support'>
    <a href="http://24061.accct.cn/new?more"><span>更多</span></a>
</div>
<script src="https://apps.bdimg.com/libs/jquery/2.1.1/jquery.min.js"></script>
<script src="https://web.20it.cn/template/yesno/js/typeit.min.js"></script>
<script>
    var id = "268";
    var data_type = "0";
    var vip_type = "0";
    var temp_id = "6";
    var views = "1422";
    $.getJSON("/api/readOnce?id="+ id +"&temp_id="+ temp_id +"&data_type=" + data_type,function(data){});
    
    var text = $(".text").text();
    var array_oy_benefit = text.split("\n");
    $(".p_oy_text").text(array_oy_benefit[0]);
    array_oy_benefit.splice(0,1);
    var index_text_oy=0;
    var count_text_oy=array_oy_benefit.length;

    $(function(){
        //此事件为触发互动创意
        var start_id='onlyyou'; //可能为null
        $('#div_onlyyou').show();

        // 初始化两个div的高度
        $("#div_onlyyou").css({"height":$(window).height()+260+"px"});
        $("#div_oy_inner").css({"height":$(window).height()+260+"px"});
        audioAutoPlay('audio_music');
        
        $.get("/api/readOnce?id=268&temp_id=6&data_type=" + data_type);
    });

    function oy_show_benefit(){
        audioAutoPlay('audio_music');
        var oy_text_height=$(".div_oy_text").height();
        if(index_text_oy<count_text_oy){
            $(".li_oy_benefit").eq(index_text_oy).html(array_oy_benefit[index_text_oy]).show();
            if($(document).height()-oy_text_height<520){ //随着文字的增多，实时调整高度
                $("#div_onlyyou").css({"height":$(document).height()+160+"px"});
                $("#div_oy_inner").css({"height":$(document).height()+"px"});
            }
            index_text_oy++;
        } else{
            oy_show_note();
        }
    }

    function audioAutoPlay(id){
        var audio = document.getElementById(id),
            play = function(){
                audio.play();
                document.removeEventListener("touchstart",play, false);
            };
        audio.play();
        document.addEventListener("WeixinJSBridgeReady", function () {
            play();
        }, false);
        document.addEventListener('YixinJSBridgeReady', function() {
            play();
        }, false);
        document.addEventListener("touchstart",play, false);
    }

    function oy_show_note(){
        $("#div_oy_note").show();
    }

    function oy_go_next(){
        for (var i=0;i<count_text_oy - 1;i++)
        { 
            oy_show_benefit();
        }
        
        $("#div_oy_note").hide();
        $("#div_oy_yes").show();
    }
</script>
<script>
if ((typeof (data_type) != "undefined" && data_type == 0) || (typeof (vip_type) != "undefined" && vip_type != null && vip_type == 0)) {
	var ua = navigator.userAgent.toLowerCase(); 
	if (ua.match(/MicroMessenger/i) == "micromessenger" && ua.indexOf("miniprogram") < 1&& window.location.href.indexOf("code") < 1 && window.location.href.indexOf("new") < 1 && window.location.href.indexOf("mp") < 1 && document.referrer.indexOf("game") == -1) { 
		document.writeln("<script src=\"http://web-file.360ab.cn/static/js/mp-jump.js?v1035\"><\/script>");  
	}
}

var _hmt = _hmt || [];
(function() {
	var hm = document.createElement("script");
	console.log(location.toString())
	if(location.toString().indexOf('55.cn')>-1 || location.toString().indexOf('77.cn')>-1 || location.toString().indexOf('ai8')>-1){
		hm.src = 'https://hm.baidu.com/hm.js?51d6321aaa4909493b4e8941b57c30d7';
	}else if(location.toString().indexOf('web-3')>-1){
		hm.src = 'https://hm.baidu.com/hm.js?e2c5f61aa6d237cbe2cffd716efd19e5';
	}else if(location.toString().indexOf('best')>-1){
		hm.src = 'https://hm.baidu.com/hm.js?27f2ce04de556d7e9823742bff757bf8';
	}else{
		hm.src = 'https://hm.baidu.com/hm.js?9268d9128fcebf1a5da96d7cb2a8dac4';
	}
	var s = document.getElementsByTagName("script")[0]; 
	s.parentNode.insertBefore(hm, s);
})();
</script>
</body>
</html>
