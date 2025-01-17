# kcal.keisan-new
html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>体重・身長・年齢の入力フォーム</title>
</head>
<body>
    <h1>体重・身長・年齢の入力フォーム</h1>
    <form>
        <label for="weight">体重 (kg):</label>
        <input type="number" id="weight" name="weight" required><br><br>

        <label for="height">身長 (cm):</label>
        <input type="number" id="height" name="height" required><br><br>

        <label for="age">年齢 (歳):</label>
        <input type="number" id="age" name="age" required><br><br>

        <label for="activity-level">活動量:</label>
        <select id="activity-level" name="activity-level" required>
            <option value="low">低い（運動不足）</option>
            <option value="moderate">中程度（週に数回の運動）</option>
            <option value="high">高い（毎日の運動）</option>
        </select><br><br>

        <input type="submit" value="送信">
    </form>
</body>
</html>
