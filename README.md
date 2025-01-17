# ダイエットコーチみっちゃん
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>推定消費カロリー計算機</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 8px;
            max-width: 400px;
        }
        input, select {
            margin-bottom: 10px;
            padding: 8px;
            width: 100%;
        }
        button {
            padding: 10px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>推定消費カロリー計算機</h1>
    <label for="gender">性別:</label>
    <select id="gender">
        <option value="male">男性</option>
        <option value="female">女性</option>
    </select>
    
    <label for="age">年齢 (歳):</label>
    <input type="number" id="age" placeholder="例: 30" min="1" required>
    
    <label for="weight">体重 (kg):</label>
    <input type="number" id="weight" placeholder="例: 70" min="1" required>
    
    <label for="height">身長 (cm):</label>
    <input type="number" id="height" placeholder="例: 175" min="1" required>
    
    <label for="activity">活動量:</label>
    <select id="activity">
        <option value="1.1">活動量が低い (デスクワーク、運動を全くしない)</option>
        <option value="1.2">活動量が標準 (立ち仕事、運動週に2〜3回)</option>
        <option value="1.3">活動量が高い (力仕事、運動週に5回以上)</option>
    </select>
    
    <button onclick="calculateBMR()">計算</button>
    
    <h2>推定消費カロリー: <span id="caloriesResult">0</span> kcal/day</h2>

    <script>
        function calculateBMR() {
            const gender = document.getElementById('gender').value;
            const age = parseInt(document.getElementById('age').value);
            const weight = parseFloat(document.getElementById('weight').value);
            const height = parseFloat(document.getElementById('height').value);
            const activityFactor = parseFloat(document.getElementById('activity').value);
            let bmr;

            // 基礎代謝の計算
            if (gender === 'male') {
                bmr = 88.362 + (13.397 * weight) + (4.799 * height) - (5.677 * age);
            } else {
                bmr = 447.593 + (9.247 * weight) + (3.098 * height) - (4.330 * age);
            }

            // 活動量を考慮した消費カロリーの計算
            const totalCalories = bmr * activityFactor;

            document.getElementById('caloriesResult').textContent = Math.round(totalCalories);
        }
    </script>
</body>
</html>
