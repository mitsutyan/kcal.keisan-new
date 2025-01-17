# kcal.keisan-new
html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>基礎代謝計算機</title>
</head>
<body>
    <h1>基礎代謝計算機</h1>
    <form id="bmrForm">
        <label for="weight">体重 (kg):</label>
        <input type="number" id="weight" required>
        
        <label for="height">身長 (cm):</label>
        <input type="number" id="height" required>
        
        <label for="age">年齢:</label>
        <input type="number" id="age" required>
        
        <label>性別:</label>
        <input type="radio" id="male" name="gender" value="male" required>
        <label for="male">男性</label>
        <input type="radio" id="female" name="gender" value="female" required>
        <label for="female">女性</label>
        
        <button type="submit">計算する</button>
    </form>
    
    <h2 id="result"></h2>

    <script>
        document.getElementById('bmrForm').addEventListener('submit', function(event) {
            event.preventDefault();

            const weight = parseFloat(document.getElementById('weight').value);
            const height = parseFloat(document.getElementById('height').value);
            const age = parseInt(document.getElementById('age').value);
            const gender = document.querySelector('input[name="gender"]:checked').value;

            let bmr;
            if (gender === 'male') {
                bmr = 66 + (13.7 * weight) + (5 * height) - (6.76 * age);
            } else {
                bmr = 655 + (9.6 * weight) + (1.8 * height) - (4.7 * age);
            }

            document.getElementById('result').innerText = `基礎代謝: ${bmr.toFixed(2)} kcal`;
        });
    </script>
</body>
</html>
