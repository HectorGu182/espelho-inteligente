<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espelho Inteligente - Transforme Seu Dia</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.2.19/tailwind.min.css">
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            let form = document.getElementById("cadastro-form");
            if (form) {
                form.addEventListener("submit", function(event) {
                    event.preventDefault(); // Evita que a página seja recarregada
                    document.getElementById('cadastro-section').style.display = 'none';
                    document.getElementById('boas-vindas-section').style.display = 'block';
                });
            }
        });

        function mostrarCriacaoAvatar() {
            document.getElementById('boas-vindas-section').style.display = 'none';
            document.getElementById('criacao-avatar-section').style.display = 'block';
        }

        function salvarAvatar() {
            alert('Seu avatar foi salvo com sucesso!');
            document.getElementById('criacao-avatar-section').style.display = 'none';
            document.getElementById('interacao-ia-section').style.display = 'block';
            iniciarNotificacoes();
        }

        function enviarMensagem() {
            var input = document.getElementById('mensagem-input');
            var mensagem = input.value;
            if (mensagem.trim() !== "") {
                var chatBox = document.getElementById('chat-box');
                var userMessage = document.createElement('p');
                userMessage.className = "text-right text-blue-600 font-semibold";
                userMessage.textContent = "Você: " + mensagem;
                chatBox.appendChild(userMessage);
                input.value = "";
                setTimeout(() => {
                    var botMessage = document.createElement('p');
                    botMessage.className = "text-left text-gray-700";
                    botMessage.textContent = "IA: Estou aqui para te ajudar! Como posso melhorar seu dia?";
                    chatBox.appendChild(botMessage);
                }, 1000);
            }
        }

        function iniciarNotificacoes() {
            if ("Notification" in window) {
                Notification.requestPermission().then(permission => {
                    if (permission === "granted") {
                        setInterval(() => {
                            new Notification("Lembrete do Espelho Inteligente", {
                                body: "Seu avatar está esperando por você! Venha interagir!",
                                icon: "https://via.placeholder.com/100"
                            });
                        }, 86400000); // Notificação diária (24h)
                    }
                });
            }
        }
    </script>
</head>
<body class="bg-gradient-to-r from-blue-500 to-purple-600 text-gray-900">
    <header class="text-center py-12 bg-gradient-to-r from-indigo-600 to-blue-500 text-white shadow-lg">
        <h1 class="text-5xl font-extrabold">Espelho Inteligente de Autoaperfeiçoamento</h1>
        <p class="mt-4 text-xl">Transforme seu dia com insights personalizados e motivação diária.</p>
    </header>
    
    <section id="cadastro-section" class="max-w-4xl mx-auto text-center py-12 px-6 bg-white rounded-lg shadow-xl mt-10">
        <h2 class="text-3xl font-bold text-purple-700">Cadastre-se para Testar</h2>
        <p class="mt-4 text-lg">Seja um dos primeiros a experimentar essa inovação!</p>
        <form id="cadastro-form" class="mt-6 bg-gray-100 p-6 rounded-lg shadow-md">
            <input type="text" name="nome" placeholder="Seu Nome" class="block w-full p-4 border border-gray-400 rounded-lg mb-4" required>
            <input type="email" name="email" placeholder="Seu Email" class="block w-full p-4 border border-gray-400 rounded-lg mb-4" required>
            <button type="submit" class="bg-gradient-to-r from-blue-500 to-indigo-600 text-white px-6 py-3 rounded-lg font-bold w-full hover:opacity-90 transition">Quero Participar</button>
        </form>
    </section>
    
    <section id="boas-vindas-section" class="max-w-4xl mx-auto text-center py-12 px-6 bg-white rounded-lg shadow-xl mt-10 hidden">
        <h2 class="text-3xl font-bold text-green-600">🎉 Bem-vindo(a) ao Espelho Inteligente! 🎉</h2>
        <p class="mt-4 text-lg">Parabéns por se cadastrar! Agora personalize sua experiência criando seu avatar.</p>
        <button onclick="mostrarCriacaoAvatar()" class="bg-gradient-to-r from-green-500 to-teal-600 text-white px-6 py-3 rounded-lg font-bold mt-6 hover:opacity-90 transition">Criar Meu Avatar</button>
    </section>
    
    <section id="criacao-avatar-section" class="max-w-4xl mx-auto text-center py-12 px-6 bg-white rounded-lg shadow-xl mt-10 hidden">
        <h2 class="text-3xl font-bold text-blue-700">🎭 Personalize Seu Avatar</h2>
        <p class="mt-4 text-lg">Escolha um avatar que represente você no Espelho Inteligente.</p>
        <input type="file" accept="image/*" class="block w-full p-4 border border-gray-400 rounded-lg mt-4">
        <button onclick="salvarAvatar()" class="bg-gradient-to-r from-blue-500 to-indigo-600 text-white px-6 py-3 rounded-lg font-bold mt-6 hover:opacity-90 transition">Salvar Avatar</button>
    </section>

    <section id="interacao-ia-section" class="max-w-4xl mx-auto text-center py-12 px-6 bg-white rounded-lg shadow-xl mt-10 hidden">
        <h2 class="text-3xl font-bold text-purple-700">🤖 Converse com sua IA</h2>
        <p class="mt-4 text-lg">Agora que seu avatar está pronto, você pode interagir com a IA do Espelho Inteligente!</p>
        <div id="chat-box" class="bg-gray-100 p-4 rounded-lg h-64 overflow-y-auto mt-4 border border-gray-300 text-left"></div>
        <input id="mensagem-input" type="text" placeholder="Digite sua mensagem..." class="block w-full p-4 border border-gray-400 rounded-lg mt-4">
        <button onclick="enviarMensagem()" class="bg-gradient-to-r from-purple-500 to-pink-600 text-white px-6 py-3 rounded-lg font-bold mt-4 hover:opacity-90 transition">Enviar</button>
    </section>
    
    <footer class="text-center py-6 bg-gradient-to-r from-indigo-700 to-blue-600 text-white mt-10 shadow-lg">
        <p class="text-lg">&copy; 2025 Espelho Inteligente. Todos os direitos reservados.</p>
    </footer>
</body>
</html>
