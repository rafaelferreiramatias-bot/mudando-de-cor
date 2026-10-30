<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Formulário Simples</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@400;500;700&display=swap" rel="stylesheet">

    <style>
        body {
            background-color: #45425A;
            font-family: Arial;
        }

        main {
            background-color: #6C7D47;
            width: 400px;
            margin: 50px auto;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 5px 5px 10px gray;
        }

        h1, h2 {
            text-align: center;
            color: #45425A;
            background-color: #ACC12F;
        }

        form {
            display: grid;
            gap: 10px;
        }

        label {
            color: white;
        }

        input[type="text"],
        input[type="date"] {
            padding: 8px;
            border-radius: 5px;
            border: 1px solid gray;
            color: #ACC12F;
            background-color: #45425A;
        }

        input[type="color"] {
            width: 60px;
            height: 40px;
            padding: 2px;
            cursor: pointer;
            border: 1px solid gray;
            border-radius: 5px;
        }

        button {
            padding: 8px;
            border-radius: 5px;
            border: 1px solid gray;
            background-color: #45425A;
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        button:hover {
            background-color: #D3C4E3;
            color: #45425A;
            transform: scale(1.08);
            box-shadow: 3px 3px 8px black;
        }

        section {
            background-color: #ACC12F;
            padding: 10px;
            border-radius: 10px;
            box-shadow: 2px 2px 5px black;
        }

        #resultado {
            color: white;
        }
    </style>
</head>

<body>

    <main>
        <h1>Formulário de Cadastro</h1>

        <form id="formulario">

            <label for="nome">Nome:</label>
            <input type="text" id="nome" required>

            <label for="nascimento">Data de nascimento:</label>
            <input type="date" id="nascimento" required>

            <label for="cor">Cor preferida:</label>
            <input type="color" id="cor" value="#000000">

            <button type="submit">Enviar</button>

        </form>

        <section>
            <h2>Dados preenchidos</h2>
            <div id="resultado"></div>
        </section>
    </main>

    <script>
        const formulario = document.getElementById("formulario");
        const resultado = document.getElementById("resultado");

        formulario.addEventListener("submit", function(event) {
            event.preventDefault();

            const nome = document.getElementById("nome").value;
            const nascimento = document.getElementById("nascimento").value;
            const cor = document.getElementById("cor").value;

            resultado.innerHTML = "";

            const pNome = document.createElement("p");
            pNome.textContent = "Nome: " + nome;

            const pNascimento = document.createElement("p");
            pNascimento.textContent = "Nascimento: " + nascimento;

            const pCor = document.createElement("p");
            pCor.textContent = "Cor preferida: " + cor;

            const amostraCor = document.createElement("div");
            amostraCor.style.backgroundColor = cor;
            amostraCor.style.width = "100px";
            amostraCor.style.height = "40px";
            amostraCor.style.border = "1px solid black";

            resultado.appendChild(pNome);
            resultado.appendChild(pNascimento);
            resultado.appendChild(pCor);
            resultado.appendChild(amostraCor);
        });
    </script>

</body>
</html>
