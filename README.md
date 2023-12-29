<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Would You Like to Go Out With Me?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f9f3f3;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            padding: 0;
        }

        .container {
            background-color: #fff;
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .header_text {
            font-size: 2.5rem;
            color: #e85a4f;
            margin-bottom: 30px;
        }

        .btn {
            background-color: #e85a4f;
            color: white;
            border: none;
            padding: 12px 30px;
            font-size: 1.2rem;
            border-radius: 30px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            margin-top: 20px;
        }

        .btn:hover {
            background-color: #d24c43;
        }

        select,
        input[type="date"] {
            padding: 12px;
            margin-top: 20px;
            border-radius: 15px;
            border: 1px solid #ddd;
            width: 100%;
            font-size: 1rem;
        }

        .teddy_animation {
            width: 120px;
            height: auto;
            margin-top: 30px;
            margin-bottom: 20px;
            animation: teddyFloat 3s infinite alternate;
        }

        @keyframes teddyFloat {
            from {
                transform: translateY(0);
            }
            to {
                transform: translateY(-15px);
            }
        }

        a {
            text-decoration: none;
            color: #e85a4f;
            font-weight: bold;
            transition: color 0.3s ease;
        }

        a:hover {
            color: #d24c43;
        }

    </style>
</head>

<body>

    <div class="container" id="initialPage">
        <h1 class="header_text">Would you like to spend a beautiful day with me?</h1>
        <img src="https://media.tenor.com/nQkh_i7bvuYAAAAi/eccomi.gif" alt="Cute Teddy" class="teddy_animation">
        <p>From <a href="https://www.instagram.com/yashsharma44_/">@yashsharma44_</a> ❤️</p>
        <button class="btn" onclick="navigateTo('yes')">Yes, I'd love to!</button>
        <button id="noButton" class="btn" onclick="navigateTo('no')">I'll pass for now...</button>
    </div>

    <div class="container" id="confirmationPage" style="display: none;">
        <h1>Select a Date and Destination</h1>
        <img src="https://media.tenor.com/sipDF8tPQ-cAAAAi/tkthao219-bubududu.gif" alt="Cute Teddy" class="teddy_animation">
        <input type="date" id="datePicker" placeholder="Select a date">
        <h3>Select a destination:</h3>
        <select id="destinationSelect">
            <option value="restaurant">Restaurant</option>
            <option value="starbucks">Starbucks</option>
            <option value="momo">Momo Date</option>
        </select>
        <button class="btn" onclick="confirmDetails()">Confirm</button>
    </div>

    <div class="container" id="finalPage" style="display: none;">
        <h1>Great! We've got a date.</h1>
        <img src="https://media.tenor.com/LX-ybOqDs5gAAAAM/dancing-teddy.gif" alt="Cute Teddy" class="teddy_animation">
        <p>We'll meet on <span id="confirmedDate"></span> at <span id="confirmedDestination"></span>. Can't wait! ❤️</p>
        <p>Till then, <a href="https://www.instagram.com/yashsharma44_/">let's talk</a> on Instagram! 📱</p>
    </div>

    <script>
        function navigateTo(choice) {
            if (choice === 'yes') {
                document.getElementById('initialPage').style.display = 'none';
                document.getElementById('confirmationPage').style.display = 'block';
            } else {
                // Handle the 'no' choice if needed
            }
        }

        function confirmDetails() {
            const selectedDate = document.getElementById('datePicker').value;
            const destination = document.getElementById('destinationSelect').value;

            document.getElementById('confirmationPage').style.display = 'none';
            document.getElementById('finalPage').style.display = 'block';

            document.getElementById('confirmedDate').innerText = selectedDate;
            document.getElementById('confirmedDestination').innerText = destination;
        }
    </script>

</body>

</html>
