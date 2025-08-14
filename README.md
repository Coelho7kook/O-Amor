echo "# O-Amor" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/Coelho7kook/O-Amor.git
git push -u origin main



<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alan ❤ Manuela</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: #d23669;
            text-align: center;
            overflow: hidden;
        }
        
        .container {
            background-color: rgba(255, 255, 255, 0.8);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            position: relative;
            z-index: 10;
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }
        
        p {
            font-size: 1.2rem;
            line-height: 1.6;
            margin-bottom: 20px;
        }
        
        .heart {
            font-size: 3rem;
            cursor: pointer;
            transition: transform 0.3s;
            margin: 20px 0;
            display: inline-block;
        }
        
        .heart:hover {
            transform: scale(1.2);
        }
        
        .message {
            font-style: italic;
            margin-top: 20px;
            min-height: 50px;
            font-size: 1.1rem;
            color: #ff4757;
        }
        
        .floating-hearts {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }
        
        .floating-heart {
            position: absolute;
            font-size: 1.5rem;
            animation: float 4s linear infinite;
            opacity: 0;
        }
        
        @keyframes float {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }
        
        footer {
            margin-top: 20px;
            font-size: 0.9rem;
            color: #666;
        }
    </style>
</head>
<body>
    <div class="floating-hearts" id="floatingHearts"></div>
    
    <div class="container">
        <h1>Alan ❤ Manuela</h1>
        
        <p>Manuela, cada dia ao seu lado é um presente que eu valorizo mais do que palavras podem expressar.</p>
        
        <p>Seu sorriso ilumina meus dias, sua voz acalma minha alma e seu amor preenche cada espaço do meu coração.</p>
        
        <div class="heart" id="mainHeart">❤</div>
        
        <div class="message" id="randomMessage"></div>
        
        <p>Você é a razão do meu sorriso, a musa dos meus sonhos e o amor da minha vida.</p>
        
        <footer>Para a mulher mais incrível do mundo, com todo meu amor - Alan</footer>
    </div>

    <script>
        const mainHeart = document.getElementById('mainHeart');
        const floatingHearts = document.getElementById('floatingHearts');
        const randomMessage = document.getElementById('randomMessage');
        
        const messages = [
            "Você é o melhor que já me aconteceu!",
            "Meu coração bate mais forte quando estou com você",
            "Amo cada detalhe seu, cada riso, cada olhar",
            "Você é minha pessoa favorita no mundo todo",
            "Nada se compara ao calor do seu abraço",
            "Sua felicidade é minha maior prioridade",
            "Você me faz querer ser um homem melhor",
            "Cada momento contigo é especial",
            "Seu amor é meu porto seguro",
            "Você é linda por dentro e por fora",
            "Amo a forma como você me entende",
            "Você é a realização de todos os meus sonhos"
        ];
        
        mainHeart.addEventListener('click', function() {
            // Criar múltiplos corações flutuantes
            for (let i = 0; i < 10; i++) {
                createFloatingHeart();
            }
            
            // Mostrar mensagem aleatória
            showRandomMessage();
        });
        
        function createFloatingHeart() {
            const heart = document.createElement('div');
            heart.innerHTML = '❤';
            heart.classList.add('floating-heart');
            
            // Posição aleatória
            const startPositionX = Math.random() * window.innerWidth;
            heart.style.left = startPositionX + 'px';
            heart.style.bottom = '-20px';
            
            // Cor aleatória
            const colors = ['#ff4757', '#ff6b81', '#ff8fa3', '#ffb8c6', '#d23669'];
            const randomColor = colors[Math.floor(Math.random() * colors.length)];
            heart.style.color = randomColor;
            
            // Tamanho aleatório
            const size = Math.random() * 2 + 1;
            heart.style.fontSize = size + 'rem';
            
            // Duração da animação aleatória
            const duration = Math.random() * 3 + 3;
            heart.style.animationDuration = duration + 's';
            
            floatingHearts.appendChild(heart);
            
            // Remover após a animação terminar
            setTimeout(() => {
                heart.remove();
            }, duration * 1000);
        }
        
        function showRandomMessage() {
            const randomIndex = Math.floor(Math.random() * messages.length);
            randomMessage.textContent = messages[randomIndex];
            
            // Efeito de fade in/out
            randomMessage.style.opacity = 0;
            setTimeout(() => {
                randomMessage.style.transition = 'opacity 0.5s';
                randomMessage.style.opacity = 1;
            }, 10);
        }
        
        // Mostrar uma mensagem inicial
        showRandomMessage();
        
        // Criar alguns corações flutuantes automaticamente
        setInterval(createFloatingHeart, 1000);
    </script>
</body>
</html>
