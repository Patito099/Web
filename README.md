# Web
Pagina de restaurante
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Restaurante Don Pancho | Información</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --azul-marino: #1e3a8a;
            --coral: #ff6b6b;
            --blanco-crema: #fffaf0;
            --gris-suave: #f1f5f9;
            --sombra: 0 8px 24px rgba(0, 0, 0, 0.1);
            --transicion: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--blanco-crema);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #333;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .header {
            background: linear-gradient(135deg, var(--azul-marino) 0%, #3b82f6 100%);
            color: white;
            text-align: center;
            padding: 4rem 1rem;
            position: relative;
            overflow: hidden;
            min-height: 40vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .header::after {
            content: "";
            background: url('https://images.unsplash.com/photo-1519046904884-53103b34b206?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80') center/cover;
            opacity: 0.15;
            position: absolute;
            top: 0;
            left: 0;
            bottom: 0;
            right: 0;
            z-index: 1;
        }

        .header-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            animation: fadeIn 1.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .header h1 {
            font-size: 3rem;
            margin: 0;
            font-weight: 700;
            letter-spacing: 1px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(30, 58, 138, 0.9);
            padding: 1rem 2rem;
            z-index: 1000;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: var(--transicion);
        }

        .navbar.scrolled {
            background: rgba(30, 58, 138, 0.98);
            padding: 0.8rem 2rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: white;
            text-decoration: none;
            display: flex;
            align-items: center;
        }

        .logo i {
            color: var(--coral);
            margin-right: 10px;
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: var(--transicion);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--coral);
        }

        .nav-links a::after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--coral);
            transition: var(--transicion);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .info-section {
            background: white;
            padding: 4rem 2rem;
            margin: 2rem auto;
            max-width: 800px;
            border-radius: 12px;
            box-shadow: var(--sombra);
            text-align: center;
        }

        .info-section h2 {
            color: var(--azul-marino);
            font-size: 2.5rem;
            margin-bottom: 2rem;
            position: relative;
        }

        .info-section h2::after {
            content: "";
            display: block;
            width: 100px;
            height: 4px;
            background: var(--coral);
            margin: 1rem auto;
        }

        .info-section p {
            font-size: 1.2rem;
            margin-bottom: 1rem;
            color: #333;
        }

        .info-section .contact-info {
            margin-top: 2rem;
        }

        .info-section .contact-info p {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .footer {
            background: var(--azul-marino);
            color: white;
            padding: 2rem;
            text-align: center;
        }

        .footer p {
            margin: 0;
            font-size: 1rem;
        }

        .qr-code {
            margin-top: 2rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1rem;
        }

        .qr-code img {
            width: 150px;
            height: 150px;
            border: 2px solid var(--coral);
            border-radius: 8px;
        }

        .qr-code p {
            font-size: 1rem;
            color: #ddd;
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }

            .navbar {
                flex-direction: column;
                padding: 1rem;
            }

            .nav-links {
                margin-top: 1rem;
            }

            .nav-links li {
                margin: 0 1rem;
            }

            .info-section {
                padding: 3rem 1.5rem;
                margin: 1rem;
            }

            .info-section h2 {
                font-size: 2rem;
            }
        }

        @media (max-width: 576px) {
            .header h1 {
                font-size: 2rem;
            }

            .nav-links {
                flex-wrap: wrap;
                justify-content: center;
            }

            .nav-links li {
                margin: 0.5rem;
            }

            .info-section p {
                font-size: 1rem;
            }

            .qr-code img {
                width: 120px;
                height: 120px;
            }
        }
    </style>
</head>
<body>
    <nav class="navbar" id="navbar">
        <a href="#" class="logo">
            <i class="fas fa-anchor"></i>
            <span>Don Pancho</span>
        </a>
        <ul class="nav-links">
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#info">Información</a></li>
        </ul>
    </nav>

    <header class="header" id="inicio">
        <div class="header-content">
            <h1>Restaurante Don Pancho</h1>
        </div>
    </header>

    <section class="info-section" id="info">
        <h2>Información del Restaurante</h2>
        <p>¡Bienvenidos a Don Pancho, un lugar que nunca olvidaras, como a tu ex¡</p>
        <h3>Horarios</h3>
        <p>Lunes a Jueves: 12:00 - 21:00</p>
        <p>Viernes y Sábado: 12:00 - 22:00</p>
        <p>Domingo: 11:00 - 20:00</p>
        <div class="contact-info">
            <h3>Contacto</h3>
            <p><i class="fas fa-map-marker-alt"></i> Malecón Costero 456, Puerto</p>
            <p><i class="fas fa-phone"></i> +52 55 9876 5432</p>
            <p><i class="fas fa-envelope"></i> contacto@guyianote.com</p>
        </div>
    </section>

    <footer class="footer">
        <p>© 2025 Restaurante Guyianote. Todos los derechos reservados.</p>
        <div class="qr-code">
            <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=https://www.guyianote.com" alt="QR Code">
            <p>Escanea para visitar nuestro sitio web</p>
        </div>
    </footer>

    <script>
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
