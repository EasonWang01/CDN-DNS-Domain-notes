# canvas

```text
<!DOCTYPE html>
<html>
<body>

<canvas id="myCanvas" width="200" height="100" style="border:1px solid #000000; background: linear-gradient(to bottom right, red, yellow);">
Your browser does not support the HTML5 canvas tag.
</canvas>

<script>
setInterval(function(){document.getElementById("myCanvas").width+= 5},1000)
</script>

</body>
</html>
```

canvas 用px為單位所以如果width屬性為%會自動轉為px，如果在style內width或height寫%則canvas的行為會亂掉

