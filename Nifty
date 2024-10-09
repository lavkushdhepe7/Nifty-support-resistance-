<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Support and Resistance Calculator</title>
    <style>
        /* Apply a clean and attractive base style */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(to right, #6dd5ed, #2193b0);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .container {
            background: linear-gradient(135deg, #43cea2, #185a9d);
            color: white;
            padding: 30px;
            border-radius: 20px;
            width: 100%;
            max-width: 420px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease;
            text-align: center;
            animation: fadeIn 1.2s ease-in-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h2 {
            font-size: 28px;
            margin-bottom: 20px;
            color: #fff;
            text-shadow: 0px 4px 8px rgba(0, 0, 0, 0.3);
        }

        label {
            font-size: 16px;
            margin: 10px 0;
            color: #fff;
            display: block;
            text-align: left;
            font-weight: 600;
        }

        input[type="number"] {
            width: 100%;
            padding: 14px;
            margin: 10px 0 20px;
            border-radius: 10px;
            border: none;
            font-size: 16px;
            background-color: rgba(255, 255, 255, 0.9);
            color: #333;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
            transition: box-shadow 0.3s ease, transform 0.2s ease;
        }

        input[type="number"]:focus {
            box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.2);
            transform: scale(1.02);
            outline: none;
        }

        button {
            width: 100%;
            padding: 15px;
            background-color: #FF7F50;
            color: white;
            font-size: 18px;
            font-weight: bold;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }

        button:hover {
            background-color: #ff6347;
            transform: translateY(-2px);
        }

        .result {
            margin-top: 30px;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 12px;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
            color: white;
        }

        .result p {
            font-size: 16px;
            margin: 8px 0;
            padding: 12px;
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 8px;
            color: #333;
            box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.1);
        }

        @media (max-width: 600px) {
            .container {
                padding: 20px;
                max-width: 90%;
            }

            h2 {
                font-size: 24px;
            }

            input[type="number"], button {
                padding: 12px;
                font-size: 16px;
            }

            .result p {
                font-size: 14px;
            }
        }
    </style>
</head>
<body>

<div class="container">
    <h2>Nifty 50 Support & Resistance Calculator</h2>
    
    <label for="high">High:</label>
    <input type="number" id="high" placeholder="Enter High">

    <label for="low">Low:</label>
    <input type="number" id="low" placeholder="Enter Low">

    <label for="close">Close:</label>
    <input type="number" id="close" placeholder="Enter Close">

    <button onclick="calculateLevels()">Calculate</button>

    <div class="result" id="result">
        <!-- Result will be shown here -->
    </div>
</div>

<script>
    function calculateLevels() {
        let high = parseFloat(document.getElementById('high').value);
        let low = parseFloat(document.getElementById('low').value);
        let close = parseFloat(document.getElementById('close').value);

        if (isNaN(high) || isNaN(low) || isNaN(close)) {
            alert("Please enter valid numbers for High, Low, and Close.");
            return;
        }

        // Calculate pivot point
        let pivot = (high + low + close) / 3;

        // Classic Resistance and Support Levels
        let r1 = 2 * pivot - low;
        let r2 = pivot + (high - low);
        let r3 = high + 2 * (pivot - low);
        let s1 = 2 * pivot - high;
        let s2 = pivot - (high - low);
        let s3 = low - 2 * (high - pivot);

        // Fibonacci Resistance and Support Levels
        let r1Fib = pivot + 0.382 * (high - low);
        let r2Fib = pivot + 0.618 * (high - low);
        let r3Fib = pivot + 1.000 * (high - low);
        let s1Fib = pivot - 0.382 * (high - low);
        let s2Fib = pivot - 0.618 * (high - low);
        let s3Fib = pivot - 1.000 * (high - low);

        // Display results
        document.getElementById('result').innerHTML = `
            <h3>Classic Pivot Levels</h3>
            <p>Pivot Point: ${pivot.toFixed(2)}</p>
            <p>Resistance 1 (R1): ${r1.toFixed(2)}</p>
            <p>Resistance 2 (R2): ${r2.toFixed(2)}</p>
            <p>Resistance 3 (R3): ${r3.toFixed(2)}</p>
            <p>Support 1 (S1): ${s1.toFixed(2)}</p>
            <p>Support 2 (S2): ${s2.toFixed(2)}</p>
            <p>Support 3 (S3): ${s3.toFixed(2)}</p>

            <h3>Fibonacci Pivot Levels</h3>
            <p>Resistance 1 (R1): ${r1Fib.toFixed(2)}</p>
            <p>Resistance 2 (R2): ${r2Fib.toFixed(2)}</p>
            <p>Resistance 3 (R3): ${r3Fib.toFixed(2)}</p>
            <p>Support 1 (S1): ${s1Fib.toFixed(2)}</p>
            <p>Support 2 (S2): ${s2Fib.toFixed(2)}</p>
            <p>Support 3 (S3): ${s3Fib.toFixed(2)}</p>
        `;
    }
</script>

</body>
</html>
