<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Corazón 3D animado con mensaje de amor - Te amo China">
    <meta name="keywords" content="corazón, 3D, animación, amor, China">
    <meta name="author" content="Corazón 3D">
    <title>❤️ Te amo China - Corazón 3D Animado ❤️</title>
    
    <!-- Open Graph para redes sociales -->
    <meta property="og:title" content="❤️ Te amo China - Corazón 3D Animado">
    <meta property="og:description" content="Hermoso corazón 3D girando con mensaje de amor">
    <meta property="og:type" content="website">
    <meta property="og:image" content="https://via.placeholder.com/1200x630/ff6b6b/ffffff?text=❤️+Te+amo+China">
    
    <!-- Favicon -->
    <link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>❤️</text></svg>">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            font-family: 'Georgia', serif;
            overflow: hidden;
            position: relative;
        }

        .container {
            perspective: 1000px;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            z-index: 5;
        }

        .heart {
            width: 200px;
            height: 180px;
            position: relative;
            transform-style: preserve-3d;
            animation: rotate 4s linear infinite, pulse 1.5s ease-in-out infinite alternate;
            cursor: pointer;
        }

        .heart::before,
        .heart::after {
            content: '';
            width: 100px;
            height: 160px;
            position: absolute;
            left: 50px;
            transform-origin: 0 100%;
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            border-radius: 50px 50px 0 0;
            box-shadow: 
                0 0 20px rgba(255, 107, 107, 0.5),
                inset -10px -10px 20px rgba(0, 0, 0, 0.2),
                inset 10px 10px 20px rgba(255, 255, 255, 0.3);
        }

        .heart::before {
            left: 50px;
            transform: rotate(-45deg) translateZ(10px);
        }

        .heart::after {
            left: 0px;
            transform: rotate(45deg) translateZ(10px);
        }

        @keyframes rotate {
            0% {
                transform: rotateY(0deg) rotateX(0deg);
            }
            25% {
                transform: rotateY(90deg) rotateX(15deg);
            }
            50% {
                transform: rotateY(180deg) rotateX(0deg);
            }
            75% {
                transform: rotateY(270deg) rotateX(-15deg);
            }
            100% {
                transform: rotateY(360deg) rotateX(0deg);
            }
        }

        @keyframes pulse {
            0% {
                transform: scale(1) rotateY(0deg);
            }
            100% {
                transform: scale(1.1) rotateY(360deg);
            }
        }

        .title {
            position: absolute;
            top: 50px;
            color: white;
            font-size: 2.5em;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
            text-align: center;
            width: 100%;
            z-index: 10;
            animation: titleGlow 3s ease-in-out infinite alternate;
        }

        @keyframes titleGlow {
            0% {
                text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7);
            }
            100% {
                text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.7), 0 0 20px rgba(255, 255, 255, 0.8);
            }
        }

        .love-message {
            position: absolute;
            bottom: 80px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(255, 255, 255, 0.95);
            color: #e74c3c;
            padding: 25px 50px;
            border-radius: 30px;
            font-size: 2.2em;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.1);
            box-shadow: 
                0 15px 40px rgba(0, 0, 0, 0.4),
                0 0 30px rgba(231, 76, 60, 0.6),
                inset 0 2px 0 rgba(255, 255, 255, 0.9);
            border: 4px solid #ff6b6b;
            animation: messageGlow 2s ease-in-out infinite alternate;
            z-index: 10;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        @keyframes messageGlow {
            0% {
                box-shadow: 
                    0 15px 40px rgba(0, 0, 0, 0.4),
                    0 0 30px rgba(231, 76, 60, 0.6),
                    inset 0 2px 0 rgba(255, 255, 255, 0.9);
                transform: translateX(-50%) scale(1);
            }
            100% {
                box-shadow: 
                    0 20px 50px rgba(0, 0, 0, 0.5),
                    0 0 40px rgba(231, 76, 60, 0.9),
                    inset 0 2px 0 rgba(255, 255, 255, 1);
                transform: translateX(-50%) scale(1.05);
            }
        }

        .love-message::before {
            content: '💕';
            position: absolute;
            left: -20px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.3em;
            animation: bounce 1.5s ease-in-out infinite;
        }

        .love-message::after {
            content: '💕';
            position: absolute;
            right: -20px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.3em;
            animation: bounce 1.5s ease-in-out infinite 0.75s;
        }

        @keyframes bounce {
            0%, 100% {
                transform: translateY(-50%) scale(1);
            }
            50% {
                transform: translateY(-70%) scale(1.3);
            }
        }

        /* Partículas flotantes */
        .particle {
            position: absolute;
            width: 6px;
            height: 6px;
            background: #ff6b6b;
            border-radius: 50%;
            animation: float 4s ease-in-out infinite;
            pointer-events: none;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0px) translateX(0px) rotate(0deg);
                opacity: 1;
            }
            25% {
                transform: translateY(-80px) translateX(30px) rotate(90deg);
                opacity: 0.8;
            }
            50% {
                transform: translateY(-120px) translateX(-20px) rotate(180deg);
                opacity: 0.6;
            }
            75% {
                transform: translateY(-80px) translateX(-40px) rotate(270deg);
                opacity: 0.8;
            }
        }

        .instructions {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            color: rgba(255, 255, 255, 0.8);
            font-size: 1em;
            text-align: center;
            z-index: 10;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .title {
                font-size: 1.8em;
                top: 30px;
            }
            
            .love-message {
                font-size: 1.5em;
                padding: 15px 30px;
                bottom: 60px;
            }
            
            .heart {
                width: 150px;
                height: 135px;
            }
            
            .heart::before,
            .heart::after {
                width: 75px;
                height: 120px;
            }
        }

        /* Efectos especiales */
        .heart:hover {
            filter: brightness(1.3) saturate(1.5) drop-shadow(0 0 20px rgba(255, 107, 107, 0.8));
        }

        .love-message:hover {
            transform: translateX(-50%) scale(1.1) !important;
            color: #c0392b;
            border-color: #c0392b;
        }

        /* Animación de entrada */
        .fade-in {
            animation: fadeIn 2s ease-in-out;
        }

        @keyframes fadeIn {
            0% {
                opacity: 0;
                transform: scale(0.5);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }
    </style>
</head>
<body>
    <div class="title fade-in">❤️ Corazón 3D Animado ❤️</div>
    
    <div class="container fade-in">
        <div class="heart"></div>
    </div>

    <div class="love-message fade-in">Te amo China</div>
    
    <div class="instructions">
        🖱️ Haz click para cambiar velocidad • 💫 Pasa el mouse para efectos especiales
    </div>

    <script>
        // Crear partículas flotantes
        function createParticles() {
            const container = document.body;
            
            for (let i = 0; i < 25; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                
                // Posición aleatoria
                const x = Math.random() * window.innerWidth;
                const y = Math.random() * window.innerHeight;
                
                particle.style.left = x + 'px';
                particle.style.top = y + 'px';
                
                // Delay aleatorio para la animación
                particle.style.animationDelay = `${Math.random() * 4}s`;
                particle.style.animationDuration = `${3 + Math.random() * 2}s`;
                
                container.appendChild(particle);
            }
        }

        // Funcionalidad interactiva
        const heart = document.querySelector('.heart');
        const loveMessage = document.querySelector('.love-message');
        let isSlowMotion = false;

        // Cambiar velocidad con click
        document.addEventListener('click', (e) => {
            if (e.target !== loveMessage) {
                heart.style.animationDuration = isSlowMotion ? '4s, 1.5s' : '8s, 3s';
                isSlowMotion = !isSlowMotion;
                
                // Efecto visual del click
                const ripple = document.createElement('div');
                ripple.style.cssText = `
                    position: absolute;
                    border-radius: 50%;
                    background: rgba(255, 107, 107, 0.6);
                    transform: scale(0);
                    animation: ripple 0.6s linear;
                    pointer-events: none;
                    left: ${e.clientX - 25}px;
                    top: ${e.clientY - 25}px;
                    width: 50px;
                    height: 50px;
                    z-index: 1000;
                `;
                
                document.body.appendChild(ripple);
                setTimeout(() => ripple.remove(), 600);
            }
        });

        // Efectos de hover en el corazón
        heart.addEventListener('mouseenter', () => {
            loveMessage.style.transform = 'translateX(-50%) scale(1.15)';
            loveMessage.style.color = '#c0392b';
            loveMessage.style.borderColor = '#c0392b';
        });

        heart.addEventListener('mouseleave', () => {
            loveMessage.style.transform = 'translateX(-50%) scale(1)';
            loveMessage.style.color = '#e74c3c';
            loveMessage.style.borderColor = '#ff6b6b';
        });

        // Efecto especial al hacer click en el mensaje
        loveMessage.addEventListener('click', (e) => {
            e.stopPropagation();
            
            // Animación especial
            loveMessage.style.animation = 'none';
            setTimeout(() => {
                loveMessage.style.animation = 'messageGlow 2s ease-in-out infinite alternate, bounce 0.8s ease-in-out';
                setTimeout(() => {
                    loveMessage.style.animation = 'messageGlow 2s ease-in-out infinite alternate';
                }, 800);
            }, 10);
            
            // Crear corazones flotantes
            for (let i = 0; i < 10; i++) {
                const miniHeart = document.createElement('div');
                miniHeart.innerHTML = '❤️';
                miniHeart.style.cssText = `
                    position: absolute;
                    left: ${e.clientX}px;
                    top: ${e.clientY}px;
                    font-size: ${Math.random() * 20 + 15}px;
                    pointer-events: none;
                    z-index: 1000;
                    animation: heartFloat ${Math.random() * 2 + 2}s ease-out forwards;
                `;
                
                document.body.appendChild(miniHeart);
                setTimeout(() => miniHeart.remove(), 4000);
            }
        });

        // Agregar estilos de animación dinámicamente
        const style = document.createElement('style');
        style.innerHTML = `
            @keyframes ripple {
                to {
                    transform: scale(4);
                    opacity: 0;
                }
            }
            
            @keyframes heartFloat {
                0% {
                    transform: translateY(0) rotate(0deg);
                    opacity: 1;
                }
                100% {
                    transform: translateY(-200px) rotate(360deg);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(style);

        // Inicializar partículas
        window.addEventListener('load', () => {
            createParticles();
            
            // Mensaje de bienvenida en consola
            console.log('❤️ ¡Bienvenido al Corazón 3D "Te amo China"! ❤️');
            console.log('🎮 Funciones disponibles:');
            console.log('   • Click en cualquier lugar: Cambiar velocidad');
            console.log('   • Hover en corazón: Efectos especiales');
            console.log('   • Click en mensaje: Lluvia de corazones');
        });

        // Efecto de teclado (Easter egg)
        let konamiCode = [];
        const konamiSequence = ['ArrowUp', 'ArrowUp', 'ArrowDown', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'ArrowLeft', 'ArrowRight'];
        
        document.addEventListener('keydown', (e) => {
            konamiCode.push(e.code);
            if (konamiCode.length > konamiSequence.length) {
                konamiCode.shift();
            }
            
            if (JSON.stringify(konamiCode) === JSON.stringify(konamiSequence)) {
                // Easter egg activado
                document.body.style.animation = 'rainbow 2s linear infinite';
                setTimeout(() => {
                    document.body.style.animation = '';
                }, 10000);
            }
        });

        // Animación rainbow para easter egg
        const rainbowStyle = document.createElement('style');
        rainbowStyle.innerHTML = `
            @keyframes rainbow {
                0% { filter: hue-rotate(0deg); }
                100% { filter: hue-rotate(360deg); }
            }
        `;
        document.head.appendChild(rainbowStyle);
    </script>
</body>
</html>
