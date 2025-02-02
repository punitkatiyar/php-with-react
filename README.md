# PHP With React

Setting up PHP with React on your local machine involves configuring a backend (PHP) and frontend (React) to work together. 

<img src="https://miro.medium.com/v2/resize:fit:686/1*E78GTfJ-GboVhLqeUAjiNQ.jpeg" width="100%" height="350px"/>

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

### Start XAMPP Server:

Open XAMPP Control Panel → Start Apache

- Visit: http://localhost/php-react-backend/index.php

```
{"message":"Hello from PHP Backend"}
```

## Step 3: Setup React Frontend

###  Create a React project in another directory:    

```
cd C:\Users\YourUserName
npx create-react-app php-react-frontend
cd php-react-frontend
```

### Modify App.js to fetch data from PHP:

```
import { useState, useEffect } from "react";

function App() {
    const [message, setMessage] = useState("");

    useEffect(() => {
        fetch("http://localhost/php-react-backend/index.php")
            .then(response => response.json())
            .then(data => setMessage(data.message))
            .catch(error => console.error("Error:", error));
    }, []);

    return (
        <div>
            <h1>React with PHP Backend</h1>
            <p>Message from backend: {message}</p>
        </div>
    );
}

export default App;
```







