# 做一個OOXX小遊戲


index.html
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" type="text/css" href="style.css" />
        <script src="https://code.jquery.com/jquery-2.2.1.min.js"></script>
        <script src="game.js"></script>
    </head>
    <body>
        <div class="board">
            <div class="cell" data-i="0"></div>
            <div class="cell" data-i="1"></div>
            <div class="cell" data-i="2"></div>
            <div class="cell" data-i="3"></div>
            <div class="cell" data-i="4"></div>
            <div class="cell" data-i="5"></div>
            <div class="cell" data-i="6"></div>
            <div class="cell" data-i="7"></div>
            <div class="cell" data-i="8"></div>
            <div style="clear: both;"></div>
        </div>
        <div class="msg">
            <div class="player player1">
                <div class="mark">&times;</div>
                <div class="arrow arrow-r"></div>
            </div>
            <div class="player player2">
                <div class="mark">&#9675;</div>
                <div class="arrow arrow-l"></div>
            </div>
            <div class="ss">
                按任意鍵開始新遊戲。
            </div>
        </div>
    </body>
</html>
```
#接著在同層目錄建造一個game.js和style.css


style.css
```
        <style>
            body {
                background-color: #d2d7d3;
            }
            .board, .msg {
                margin: 0 auto;
                margin-top: 60px;
                width: 80%;
                max-width: 800px;    
            }
            .board {
                position: relative;
                background-color: #fde3a7;
            }

            .cell {
                width: 30%;
                height: 20px;
                margin: 1.6%;
                float: left;
                background-color: #4ecdc4;
                cursor: pointer;
                text-align: center;
            }
            .cell:hover {
                box-shadow: 2px 2px 0 #1ba39c;
            }
            .cell.win {
                color: red;
            }

            .player {
                width: 50%;
                height: 80px;
                float: left;
                text-align: center;
            }
            .arrow, .mark {
                width: 50%;
            }
            .player1 > div {
                float: right;
            }
            .player2 > div {
                float: left;
            }
            .arrow {
                width: 0; 
                height: 0; 
                border-top: 40px solid transparent;
                border-bottom: 40px solid transparent;
            }
            .arrow.inv {
                visibility: hidden;
            }
            .arrow-r {
                border-left: 40px solid #4ecdc4;
            }
            .arrow-l {
                border-right: 40px solid #4ecdc4;    
            }
            .mark {
                font-size: 80px;
                line-height: 80px;
            }
            .ss {
                clear: both;
                font-size: 36px;
                text-align: center;
                font-family: sans-serif;
                padding: 32px 0;
            }
			@media (max-width: 600px) {
                .board {
                    width: 90%;
                }
            }
        </style>
```
#接著開始寫邏輯的部分game.js

1.東西都放在這裡面，代表載入完DOM後才會執行
```
$(function() {

});
```
2.我們讓cell(九宮格)的高度會保持寬度固定，以及定義我們需要的變數
```
 var cells = $('.cell');
  //圈叉符號
    var symbols = ['&times;', '&#9675;'];
  //目前為第幾輪
    var currentStep = 0,
        currentState = {};
    var gameOver = true;
	//調整大小
 var winResizeHandler = function() {
        var c = cells;
        var w = c.width();
        c.css({
            'line-height': w * 0.92 + 'px',
            'font-size': w + 'px'
        }).height(w);
    };
	winResizeHandler();
```
3.接著定義點擊cell要發生的事

```
//接著定義點擊cell要發生的事
	   cells.click(function(e) {
        if (!gameOver) {
            var $this = $(this);//簡寫
            var i = $this.data('i');//cell中自定義的屬性data-i
            if (currentState[i] === null) {
                var s = symbols[currentStep++ % 2];//symbols[0]為叉symbols[1]為圈
                currentState[i] = s;
                $this.html(s);
                for (var j = 0, len = potentialCombos[i].length; j < len; j++) {
                    if (checkCombo(winningCombos[potentialCombos[i][j]])) {
                        console.log(s + 'won');
                        gameOver = true;
                        $('.ss').text('按任意鍵重新開始');
                        return;
                    }
                }
                if (currentStep === 9) {
                    gameOver = true;
                    $('.ss').text('平手! 按任意鍵重新開始');
                    return;
                }
                showArrow(currentStep);
            }
        }
    });
```
4.回到上面定義potentialCombos、winningCombos、checkCombo、  showArrow
```
  //哪些情況可能獲勝
    var winningCombos = {
        combo0: [0, 1, 2],
        combo1: [3, 4, 5],
        combo2: [6, 7, 8],
        combo3: [0, 3, 6],
        combo4: [1, 4, 7],
        combo5: [2, 5, 8],
        combo6: [0, 4, 8],
        combo7: [2, 4, 6]
    };
  ///點了哪個方格後所需要檢查的組合
    var potentialCombos = {
        0: ['combo0', 'combo3', 'combo6'],
        1: ['combo0', 'combo4'],
        2: ['combo0', 'combo5', 'combo7'],
        3: ['combo1', 'combo3'],
        4: ['combo1', 'combo4', 'combo6', 'combo7'],
        5: ['combo1', 'combo5'],
        6: ['combo2', 'combo3', 'combo7'],
        7: ['combo2', 'combo4'],
        8: ['combo2', 'combo5', 'combo6'],
    };
/////圈叉的圖案轉換，先叉後圈
    var showArrow = function(p) {
        if (p % 2 === 0) {
            $('.player1 > .arrow').removeClass('inv');
            $('.player2 > .arrow').addClass('inv');        
        } else {
            $('.player1 > .arrow').addClass('inv');
            $('.player2 > .arrow').removeClass('inv');            
        }
    };
	
	
	
	
	   var checkCombo = function(a) {
        var a0 = currentState[a[0]],///檢查陣列中三個元素是否都等於圈或叉
            a1 = currentState[a[1]],
            a2 = currentState[a[2]];
        var w = (a0 === a1 && a1 === a2);
        if (w) {//加上win class讓該條顏色變紅色
            $('.cell[data-i="' + a[0] + '"]').addClass('win');
            $('.cell[data-i="' + a[1] + '"]').addClass('win');
            $('.cell[data-i="' + a[2] + '"]').addClass('win');
        }
        return w;
    };
```
5.最後定義遊戲要在剛開始時初始化，和gameover時點擊任意按鍵初始化

```
	///初始化遊戲
    var initGame = function() {
      ///如果遊戲結束清空九公格
        if (gameOver) {
          //清空圈叉圖案
            cells.empty();
            for (var i = 0; i < 9; i ++) {
                currentState[i] = null;
            }
          //還原步數
            currentStep = 0;
          //還原圖案為叉
            showArrow(currentStep);
            gameOver = false;
            cells.removeClass('win');
            $('.ss').text('');
        }
    };
  //載入完網頁先執行初始化
    initGame();
	
	    $(window)
        .resize(winResizeHandler)//縮放螢幕後自動調整方塊大小
        .keydown(function(e) {//點擊任意鍵初始化
            e.preventDefault();
            initGame();
        });
        
});
```



完整版
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <style>
            body {
                background-color: #d2d7d3;
            }
            .board, .msg {
                margin: 0 auto;
                margin-top: 60px;
                width: 80%;
                max-width: 800px;    
            }
            .board {
                position: relative;
                background-color: #fde3a7;
            }

            .cell {
                width: 30%;
                height: 20px;
                margin: 1.6%;
                float: left;
                background-color: #4ecdc4;
                cursor: pointer;
                text-align: center;
            }
            .cell:hover {
                box-shadow: 2px 2px 0 #1ba39c;
            }
            .cell.win {
                color: red;
            }

            .player {
                width: 50%;
                height: 80px;
                float: left;
                text-align: center;
            }
            .arrow, .mark {
                width: 50%;
            }
            .player1 > div {
                float: right;
            }
            .player2 > div {
                float: left;
            }
            .arrow {
                width: 0; 
                height: 0; 
                border-top: 40px solid transparent;
                border-bottom: 40px solid transparent;
            }
            .arrow.inv {
                visibility: hidden;
            }
            .arrow-r {
                border-left: 40px solid #4ecdc4;
            }
            .arrow-l {
                border-right: 40px solid #4ecdc4;    
            }
            .mark {
                font-size: 80px;
                line-height: 80px;
            }
            .ss {
                clear: both;
                font-size: 36px;
                text-align: center;
                font-family: sans-serif;
                padding: 32px 0;
            }
			@media (max-width: 600px) {
                .board {
                    width: 90%;
                }
            }
        </style>
    </head>
    <body>
        <div class="board">
            <div class="cell" data-i="0"></div>
            <div class="cell" data-i="1"></div>
            <div class="cell" data-i="2"></div>
            <div class="cell" data-i="3"></div>
            <div class="cell" data-i="4"></div>
            <div class="cell" data-i="5"></div>
            <div class="cell" data-i="6"></div>
            <div class="cell" data-i="7"></div>
            <div class="cell" data-i="8"></div>
            <div style="clear: both;"></div>
        </div>
        <div class="msg">
            <div class="player player1">
                <div class="mark">&times;</div>
                <div class="arrow arrow-r"></div>
            </div>
            <div class="player player2">
                <div class="mark">&#9675;</div>
                <div class="arrow arrow-l"></div>
            </div>
            <div class="ss">
                點擊開始遊戲
            </div>
        </div>
        <script src="jquery-1.11.3.min.js"></script>
        <script>

$(function() {
//1
 var cells = $('.cell');
  //圈叉符號
    var symbols = ['&times;', '&#9675;'];
  //目前為第幾輪
    var currentStep = 0,
        currentState = {};
    var gameOver = true;
	//調整大小
 var winResizeHandler = function() {
        var c = cells;
        var w = c.width();
        c.css({
            'line-height': w * 0.92 + 'px',
            'font-size': w + 'px'
        }).height(w);
    };
	winResizeHandler();
	//4
	  //哪些情況可能獲勝
    var winningCombos = {
        combo0: [0, 1, 2],
        combo1: [3, 4, 5],
        combo2: [6, 7, 8],
        combo3: [0, 3, 6],
        combo4: [1, 4, 7],
        combo5: [2, 5, 8],
        combo6: [0, 4, 8],
        combo7: [2, 4, 6]
    };
  ///點了哪個方格後所需要檢查的組合
    var potentialCombos = {
        0: ['combo0', 'combo3', 'combo6'],
        1: ['combo0', 'combo4'],
        2: ['combo0', 'combo5', 'combo7'],
        3: ['combo1', 'combo3'],
        4: ['combo1', 'combo4', 'combo6', 'combo7'],
        5: ['combo1', 'combo5'],
        6: ['combo2', 'combo3', 'combo7'],
        7: ['combo2', 'combo4'],
        8: ['combo2', 'combo5', 'combo6'],
    };
/////圈叉的圖案轉換，先叉後圈
    var showArrow = function(p) {
        if (p % 2 === 0) {
            $('.player1 > .arrow').removeClass('inv');
            $('.player2 > .arrow').addClass('inv');        
        } else {
            $('.player1 > .arrow').addClass('inv');
            $('.player2 > .arrow').removeClass('inv');            
        }
    };
	
	
	
	
	//3
	   var checkCombo = function(a) {
        var a0 = currentState[a[0]],///檢查陣列中三個元素是否都等於圈或叉
            a1 = currentState[a[1]],
            a2 = currentState[a[2]];
        var w = (a0 === a1 && a1 === a2);
        if (w) {//加上win class讓該條顏色變紅色
            $('.cell[data-i="' + a[0] + '"]').addClass('win');
            $('.cell[data-i="' + a[1] + '"]').addClass('win');
            $('.cell[data-i="' + a[2] + '"]').addClass('win');
        }
        return w;
    };
	
	
	
	
	
//2
	//接著定義點擊cell要發生的事
	   cells.click(function(e) {
        if (!gameOver) {
            var $this = $(this);//簡寫
            var i = $this.data('i');//cell中自定義的屬性data-i
            if (currentState[i] === null) {
                var s = symbols[currentStep++ % 2];//symbols[0]為叉symbols[1]為圈
                currentState[i] = s;
                $this.html(s);
                for (var j = 0, len = potentialCombos[i].length; j < len; j++) {
                    if (checkCombo(winningCombos[potentialCombos[i][j]])) {
                        console.log(s + 'won');
                        gameOver = true;
                        $('.ss').text('按任意鍵重新開始');
                        return;
                    }
                }
                if (currentStep === 9) {
                    gameOver = true;
                    $('.ss').text('平手! 按任意鍵重新開始');
                    return;
                }
                showArrow(currentStep);
            }
        }
    });
	
	//回到上面定義potentialCombos winningCombos  checkCombo  showArrow
	
	//5
	//最後定義遊戲要在剛開始時初始化，和gameover時點擊任意按鍵初始化
	///初始化遊戲
    var initGame = function() {
      ///如果遊戲結束清空九公格
        if (gameOver) {
          //清空圈叉圖案
            cells.empty();
            for (var i = 0; i < 9; i ++) {
                currentState[i] = null;
            }
          //還原步數
            currentStep = 0;
          //還原圖案為叉
            showArrow(currentStep);
            gameOver = false;
            cells.removeClass('win');
            $('.ss').text('');
        }
    };
  //載入完網頁先執行初始化
    initGame();
	
	    $(window)
        .resize(winResizeHandler)//縮放螢幕後自動調整方塊大小
        .keydown(function(e) {//點擊任意鍵初始化
            e.preventDefault();
            initGame();
        });
        
});

        </script>
    </body>
</html>

```
##想在點擊時加入音效呢?

先嵌入一個音效標籤
```
<audio id="audio1" hidden="true" src="http://taira-komori.jpn.org/sound_os/animals01/burp1.mp3" controls preload="auto" autobuffer >
```



接著在cells.click裡面加入
```

document.getElementById('audio1').play();
```