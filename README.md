<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rate Our Business - Rangoli Garments</title>
    <style>
        /* Global Styles */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }
        body {
            text-align: center;
            padding: 20px;
            background: #f8f9fa;
        }
        h1 {
            margin-bottom: 10px;
            font-size: 28px;
        }
        .shop-logo {
            max-width: 10%; /* Prevents overflow */
            height: auto; /* Keeps aspect ratio */
            display: block;
            margin: 0 auto 20px; /* Centers the image */
            border-radius: 0; /* Ensures rectangle shape */
        }
        .container {
            width: 90%; /* Instead of max-width 500px, this allows it to shrink on smaller screens */
            max-width: 500px; /* Ensures it doesn’t get too wide */
            margin: auto;
            padding: 20px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        .section {
            margin-bottom: 25px;
        }
        .rating {
            direction: rtl;
            display: flex;
            justify-content: center;
            margin-bottom: 10px;
        }
        .rating input {
            display: none;
        }
        .rating label {
            font-size: 30px;
            color: #ccc;
            cursor: pointer;
            transition: 0.3s;
        }
        .rating input:checked ~ label,
        .rating label:hover,
        .rating label:hover ~ label {
            color: gold;
            transform: scale(1.1);
        }
        .comment-box {
            width: 100%;
            height: 80px;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            resize: none;
            font-size: 14px;
        }
        button {
            background-color: #28a745;
            color: white;
            border: none;
            padding: 12px;
            font-size: 16px;
            width: 100%;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
        }
        button:disabled {
            background-color: gray;
            cursor: not-allowed;
        }
        button:hover:enabled {
            background-color: #218838;
        }
        .thank-you {
            display: none;
            font-size: 20px;
            color: green;
            font-weight: bold;
            margin-top: 20px;
        }
        @media (max-width: 600px) {
            .rating label {
                font-size: 24px; /* Slightly smaller stars */
            }
            .container {
                width: 95%; /* More space on small screens */
            }
            button {
                width: 100%; /* Ensures full width */
                max-width: 400px; /* Prevents it from being too big */
                margin: auto;
                display: block;
            }
        }
    </style>
</head>
<body>

    <!-- Shop Logo -->
    <img src="logo.PNG" alt="Rangoli Garments Logo" class="shop-logo">


    <h1>Rate Rangoli Garments</h1>

    <div class="container" id="feedbackForm">
        
        <!-- Google Rating Section -->
        <div class="section">
            <h2>Google Rating</h2>
            <div class="rating" id="googleRating">
                <input type="radio" name="googleStars" value="5" id="g5"><label for="g5">★</label>
                <input type="radio" name="googleStars" value="4" id="g4"><label for="g4">★</label>
                <input type="radio" name="googleStars" value="3" id="g3"><label for="g3">★</label>
                <input type="radio" name="googleStars" value="2" id="g2"><label for="g2">★</label>
                <input type="radio" name="googleStars" value="1" id="g1"><label for="g1">★</label>
            </div>
            <textarea class="comment-box" placeholder="Optional Comment (Google)"></textarea>
        </div>

        <!-- Justdial Rating Section -->
        <div class="section">
            <h2>Justdial Rating</h2>
            <div class="rating" id="justdialRating">
                <input type="radio" name="justdialStars" value="5" id="j5"><label for="j5">★</label>
                <input type="radio" name="justdialStars" value="4" id="j4"><label for="j4">★</label>
                <input type="radio" name="justdialStars" value="3" id="j3"><label for="j3">★</label>
                <input type="radio" name="justdialStars" value="2" id="j2"><label for="j2">★</label>
                <input type="radio" name="justdialStars" value="1" id="j1"><label for="j1">★</label>
            </div>
            <textarea class="comment-box" placeholder="Optional Comment (Justdial)"></textarea>
        </div>

        <!-- Submit Button -->
        <button id="submitBtn" disabled>Submit</button>
    </div>

    <!-- Thank You Message -->
    <div id="thankYouMessage" class="thank-you">Thank you for your feedback! 😊</div>

    <script>
        function validateRatings() {
            const googleChecked = document.querySelector('input[name="googleStars"]:checked');
            const justdialChecked = document.querySelector('input[name="justdialStars"]:checked');
            document.getElementById('submitBtn').disabled = !(googleChecked && justdialChecked);
        }

        document.querySelectorAll('input[name="googleStars"], input[name="justdialStars"]').forEach(input => {
            input.addEventListener('change', validateRatings);
        });

        document.getElementById('submitBtn').addEventListener('click', function() {
            // Hide the feedback form
            document.getElementById('feedbackForm').style.display = 'none';

            // Show thank you message
            document.getElementById('thankYouMessage').style.display = 'block';

            // Open Google & Justdial review links in new tabs
            window.open("https://g.page/r/Celzrcrr0HUoEBM/review", "_blank");
            setTimeout(() => {
                window.open("https://jsdl.in/RSL-IXE1742469116", "_blank");
            }, 1000);
        });
    </script>

</body>
</html>
