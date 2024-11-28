<h1><a href="https://projetosimpacta.github.io/SistemaPW/">Kitty Delivery:</a></h1>
Bem-vindo ao **Kitty Delivery**! Este é um site de delivery de lanches inspirado na adorável Hello Kitty. Aqui, você pode explorar uma deliciosa seleção de lanches e doces, todos com um toque especial da nossa personagem favorita.

## Tecnologias Utilizadas

Este projeto foi desenvolvido utilizando as seguintes tecnologias:

- **HTML**: Para a estrutura do site.
- **CSS**: Para o estilo e design visual, garantindo uma experiência amigável e encantadora.
- **JavaScript**: Para interatividade e funcionalidades dinâmicas.

## Segurança no Cadastro

O **Kitty Delivery** prioriza a segurança dos dados dos usuários. O cadastro é realizado em cima da API do professor, garantindo que as informações sejam transmitidas e armazenadas de forma segura. Aqui estão alguns aspectos importantes da segurança implementada:

- **Validação de Campos**: Todos os campos do formulário de cadastro são verificados para garantir que as informações fornecidas estejam corretas e completas. Isso ajuda a prevenir erros e a garantir que os dados sejam válidos antes de serem enviados para a API.

- **Criptografia de Dados**: Os dados sensíveis, como senhas, são criptografados antes de serem armazenados ou transmitidos, protegendo as informações pessoais dos usuários.

- **Comunicação Segura**: A comunicação com a API é feita através de HTTPS, garantindo que todos os dados sejam transmitidos de forma segura e protegida contra interceptações.

Esperamos que você tenha uma experiência deliciosa com o Kitty Delivery! 🍰💖


function getWeather() {
    const resultDiv = document.getElementById("result"); 

    const apiKey = "2c9c503160794ddf927211625242711";

    const requestOptions = {
        method: "GET",
        redirect: "follow"
        
    };

    fetch('http://api.weatherapi.com/v1/current.json?key=2c9c503160794ddf927211625242711&q=s%C3%A3o%20paulo')

        .then((response) => {
            return response.json();
        })

        .then((data) => {
            const { region, country } = data.location;
            const { temp_c, condition } = data.current;

        
            resultDiv.innerHTML = `
                <img src="https:${condition.icon}" alt="${condition.text}"><br>
                <span id="temp"><strong>${temp_c}°C</strong></span><br>
                <strong> ${region}, ${country}</strong><br>
                Condição: <strong>${condition.text}</strong>
                `;
        })
    
}
