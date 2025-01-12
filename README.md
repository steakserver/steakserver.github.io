<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>SteakServer Support</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }
        h1 {
            margin: 0;
        }
        .content {
            padding: 20px;
        }
        .server-info {
            background-color: #fff;
            padding: 15px;
            margin-bottom: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .form-container {
            background-color: #fff;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        input, textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        button {
            padding: 10px 20px;
            background-color: #333;
            color: #fff;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background-color: #555;
        }
    </style>
</head>
<body>

<header>
    <h1>SteakServer - Minecraft Support</h1>
</header>

<div class="content">
    <div class="server-info">
        <h2>Welcome to SteakServer!</h2>
        <p>Join our friendly survival server at: <strong>steakserver.feathermc.gg</strong></p>
        <p>Our server offers the following commands:</p>
        <ul>
            <li><strong>/spawn</strong> - Teleport to the spawn area</li>
            <li><strong>/warp</strong> - Access server warps</li>
            <li><strong>/dailyquests</strong> - Daily quests to earn rewards</li>
        </ul>
    </div>

    <div class="form-container">
        <h2>Contact Support</h2>
        <form id="support-form">
            <input type="text" id="name" name="name" placeholder="Your Name" required>
            <input type="email" id="email" name="email" placeholder="Your Email" required>
            <textarea id="message" name="message" rows="5" placeholder="Your Message" required></textarea>
            <button type="submit">Send Message</button>
        </form>
    </div>
</div>

<!-- Include EmailJS SDK -->
<script type="text/javascript" src="https://cdn.emailjs.com/dist/email.min.js"></script>
<script>
    (function() {
        emailjs.init("YOUR_USER_ID");  // Replace with your EmailJS user ID
    })();

    // Form submission handler
    document.getElementById("support-form").addEventListener("submit", function(event) {
        event.preventDefault(); // Prevent the form from submitting the default way

        const form = event.target;

        emailjs.sendForm("YOUR_SERVICE_ID", "YOUR_TEMPLATE_ID", form)
            .then(function(response) {
                alert("Message sent successfully!");
                form.reset(); // Reset form after submission
            }, function(error) {
                alert("Failed to send the message. Please try again.");
            });
    });
</script>

</body>
</html>
