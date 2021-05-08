# 泰山職訓前端班威力彩作業
使用上課練習完成的 function 製作威力彩號碼產生器  
將隨機出的數字用 `document.write()` 顯示在網頁上  

威力彩規則:
- A 區 1~38 取 6 個數字
- B 區 1~8 取 1 個數字


<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <script>
        let list_a = []
        let list_a_sub = []
        let list_b = []

        for (let i = 1; i <= 38; i++) {
            list_a_sub.push(i)
        }
        for (let i = 1; i <= 6; i++) {
            let index = Math.round(Math.random() * list_a_sub.length)
            let rad_a = list_a_sub[index]
            list_a_sub.splice(index, 1)
            list_a.push(' ' + rad_a)
        }
        list_a.sort()
        list_a = list_a.sort((a, b) => {
            return a - b;
        })

        let rad_b = Math.round(Math.random() * 8)
        list_b.push(rad_b)

        document.write(`本期的威力彩開獎號碼為:<br><br>A區: ${list_a}<br><br>B區: ${list_b}`)
    </script>
</body>

</html>
