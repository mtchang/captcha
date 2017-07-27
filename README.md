# 修改原本的 php captcha 成為更簡單的版本, 提供 base64 影像格式的輸出。
# mtchang.tw@gmail.com
# 

# cool-php-captcha
This is the official GitHub project from code.google.com/p/cool-php-captcha



This project generates friendly captcha images. This project provides the SimpleCaptcha class.
Some fetures are: Background and foreground colors, dictionary words, non-dictionary random words, blur, shadows, JPEG and PNG support.


Basic example
-------------

* 只要執行 captchabase64.php 或 captcha.php 程式
* 在  session 內，就會有對應於 captcha 的字串 $_SESSION['captcha']
* 底下範例透過 jquery post 呼叫 captchabase64.php 產生的 images base64 code 來生成 image 檔案

```php
<?php
session_start();

?>
<html>
<head>
<script
  src="http://code.jquery.com/jquery-1.12.4.min.js"
  integrity="sha256-ZosEbRLbNQzLpnKIkEdrPv7lOy9C27hHQ+Xp8a4MxAQ="
  crossorigin="anonymous"></script>
</head>
<body>

<input name="captcha" id="captcha_input" type="text" size="10"  maxlength="4">

<span id="show_captcha">
<img src="https://www.google.com/recaptcha/intro/images/hero-recaptcha-demo.gif" id="captcha"  height="20" width="65" >
</span>

<script>
$(document).ready(function() {

$('#captcha_input').click(function(){
	$.post( 'captchabase64.php', function( captchabase64data ) {
		var img_cpatcha_html = '<img src='+captchabase64data+' id="captcha"  height="20" width="58" >';
		$('#show_captcha').html(img_cpatcha_html);
	});

});

});
</script>



<body>


```



