```html
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <title>JS 變更按鈕文字</title>
</head>
<body>

    <!-- 1. 設定一個按鈕，並給它一個 ID -->
    <button id="myButton">點我變文字</button>

    <script>
        // 2. 獲取按鈕元素
        const myButton = document.getElementById('myButton');

        // 3. 初始文字 (可選，如果 HTML 已有文字可省略)
        let originalText = '點我變文字';
        let newText = '文字變了！';

        // 4. 點擊事件監聽
        myButton.addEventListener('click', function() {
            // 5. 檢查按鈕的當前文字
            if (myButton.innerText === originalText) {
                // 如果是原始文字，就改成新文字
                myButton.innerText = newText;
            } else {
                // 否則 (已是新文字)，就變回原始文字
                myButton.innerText = originalText;
            }
        });
    </script>

</body>
</html>
```
```html
<!DOCTYPE html>
<html>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const myButton = document.getElementById('myButton');
            const displayArea = document.getElementById('displayArea');
            let isToggled = false; // 追蹤狀態

            myButton.addEventListener('click', function() {
                if (!isToggled) {
                    // 第一次點擊：變更按鈕和顯示區文字
                    myButton.innerText = '變成了！';
                    displayArea.innerText = '按鈕被點擊了，文字變換！';
                    isToggled = true;

                    // 點擊後延遲 2 秒再變回
                    setTimeout(function() {
                        myButton.innerText = '點擊我切換文字'; // 變回原始按鈕文字
                        displayArea.innerText = '這是原始文字'; // 變回原始顯示文字
                        isToggled = false; // 重置狀態
                    }, 2000); // 2000毫秒 = 2秒
                }
                // 如果 isToggled 已經是 true，就不做任何事，等待 2 秒後自動恢復
            });
        });
    </script>

<head>
    <title>JS 文字切換</title>
    <style>
        #displayArea { margin-top: 20px; font-size: 18px; color: blue; }
        #myButton { padding: 10px 20px; cursor: pointer; }
    </style>
</head>

<body>
    <button id="myButton">點擊我切換文字</button>
    <div id="displayArea">這是原始文字</div>

    <script src="script.js"></script>
</body>
</html>
```
