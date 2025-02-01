# PHP With React

Setting up PHP with React on your local machine involves configuring a backend (PHP) and frontend (React) to work together. 

## Step 1: Install Required Software
Ensure you have the following installed:

- XAMPP (or any PHP server) → Download
- Node.js (for React) → Download

## Step 2: Setup PHP Backend

Create a new PHP project inside the htdocs directory of XAMPP:

```
cd C:\xampp\htdocs
mkdir php-react-backend
cd php-react-backend

```

### Create an API using PHP (inside php-react-backend folder):

Create a file index.php

```
<?php
header("Access-Control-Allow-Origin: *");
header("Access-Control-Allow-Headers: *");
header("Content-Type: application/json");

$data = [
    "message" => "Hello from PHP Backend"
];

echo json_encode($data);
?>

```
