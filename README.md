<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yeah, you found me</title>
    <link href="https://fonts.googleapis.com/css2?family=Questrial&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Questrial', sans-serif;
            background-color: black;
            color: #FF5252;
            text-align: center;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            position: relative;
        }
        h1 {
            font-size: 3rem;
            color: #B22222;
            margin-bottom: 20px;
        }
        p {
            color: #CCCCCC;
            font-size: 1.2rem;
            margin: 10px 0;
        }
        .image-container {
            display: inline-block;
        }
        .image-container .main-image {
            width: 150px;
            border-radius: 10px;
        }
        .polaroid-image {
            position: absolute;
            bottom: 10px;
            right: 10px;
            width: 100px;
            border-radius: 10px;
        }
        .top-left-image {
            position: absolute;
            top: 10px;
            left: 10px;
            width: 100px;
            border-radius: 10px;
        }
        .password-container {
            margin-top: 20px;
        }
        input {
            padding: 10px;
            margin: 10px;
            font-size: 1rem;
            width: 250px;
            border: 2px solid #444;
            border-radius: 5px;
            background-color: #222;
            color: #CCCCCC;
        }
        button {
            padding: 10px 20px;
            font-size: 1rem;
            background-color: #B22222;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #FF5252;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <h1>Yeah, you found me</h1>
    <div class="image-container">
        <img src="https://i.postimg.cc/6yCGtGWm/2023-10-29-133906.jpg" alt="Main Image" class="main-image">
    </div>
    <p>Meow.</p>
    <p>(waiting for something to happen?)</p>
    <p>Meow. again..</p>
    <p>(Just enter password)</p>
    <div class="password-container">
        <input type="password" id="passwordInput" placeholder="Enter the password">
        <button onclick="checkPassword()">Submit</button>
    </div>
    <div id="incorrectLink" class="hidden">
        <p>Incorrect password. Redirecting to a video...</p>
    </div>
    <img src="https://i.postimg.cc/jDsCTgkD/2023-10-29-133857.jpg" alt="Polaroid Image" class="polaroid-image">
    <img src="https://i.postimg.cc/7C1C05tW/2023-10-29-133915.jpg" alt="Top Left Image" class="top-left-image">
    <script>
        // Função para ofuscar e codificar a senha
        function encodePassword(password) {
            // Codifica a senha com uma técnica simples de XOR e transformação
            const secret = [];
            for (let i = 0; i < password.length; i++) {
                // Cada caractere é XOR com um valor secreto para ofuscar a senha
                secret.push(password.charCodeAt(i) ^ 87); // 87 é um valor de chave simples para ofuscação
            }
            return secret.join('-');
        }

        // Função para verificar a senha inserida
        function checkPassword() {
            const input = document.getElementById("passwordInput").value;
            
            // A senha correta está "ofuscada" e precisa ser decodificada para comparação
            const correctEncoded = encodePassword("May we meet here?");

            // Ofusca a entrada do usuário e compara com a senha codificada
            if (encodePassword(input) === correctEncoded) {
                window.location.href = "https://i.postimg.cc/MKpYM5PB/Screenshot-2024-12-12-21-18-37-467-com-google-android-apps-photos.jpg";
            } else {
                document.getElementById("incorrectLink").classList.remove("hidden");
                setTimeout(() => {
                    window.location.href = "https://youtu.be/hI-6CkjlkEE";
                }, 500);
            }
        }
    </script>
</body>
</html>
