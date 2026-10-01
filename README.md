# Codes
sudo mkdir -p /var/www/html

sudo apt install apache2 php libapache2-mod-php mysql-server php-mysql -y
sudo apt install apache2 -y

sudo nano /var/www/html/submit.php

sudo nano /var/www/html/submit.php

<?php
$conn = new mysqli("localhost", "root", "", "web_project");

if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

$name = $_POST['name'];
$email = $_POST['email'];
$message = $_POST['message'];

$sql = "INSERT INTO contacts (name, email, message) VALUES ('$name', '$email', '$message')";

if ($conn->query($sql) === TRUE) {
    echo "✅ Data saved successfully!";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}

$conn->close();
?>
```[cite: 1]
CREATE USER 'webuser'@'localhost' IDENTIFIED BY 'password123';
GRANT ALL PRIVILEGES ON web_project.* TO 'webuser'@'localhost';
FLUSH PRIVILEGES;

mkdir ngrok-setup-sai
   cd ngrok-setup-sai

wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz
   tar -xvzf ngrok-v3-stable-linux-amd64.tgz

sudo mv ngrok /usr/local/bin/

ngrok config add-authtoken <YOUR_AUTHTOKEN>

ngrok config add-authtoken 3K3NP7sTN3MNE6L35r6xi3Db2eP_5uAqExGEy8Uq8cyn9m513

ngrok http 80

mkdir contact-form-frontend
cd contact-form-frontend

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact Form</title>
</head>
<body>
    <h1>Contact Us</h1>
    <!-- Replace the action URL with your VM IP or Ngrok forwarding URL -->
    <form action="http://<VM_IP_OR_NGROK_URL>/submit.php" method="POST">
        <input type="text" name="name" placeholder="Enter your name" required><br><br>
        <input type="email" name="email" placeholder="Enter your email" required><br><br>
        <textarea name="message" placeholder="Enter your message"></textarea><br><br>
        <button type="submit">Submit</button>
    </form>
</body>
</html>


sudo mysql -e "USE web_project; SELECT * FROM contacts;"
ngrok config add-authtoken 3K6DrcCEPaozoOELYnXwVM5OEOT_5cP5KW3KBJsN9uDLbE7RR


