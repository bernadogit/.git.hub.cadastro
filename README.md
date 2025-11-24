<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Conecta Oportunidades - Cadastro</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6366f1;
            --secondary: #10b981;
            --accent: #f59e0b;
            --dark: #0f172a;
            --darker: #020617;
            --light: #f8fafc;
            --text: #e2e8f0;
            --text-light: #94a3b8;
            --success: #059669;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
        }

        body {
            background: linear-gradient(135deg, var(--darker) 0%, var(--dark) 100%);
            color: var(--text);
            line-height: 1.6;
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Partículas animadas */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .particle {
            position: absolute;
            background: rgba(99, 102, 241, 0.15);
            border-radius: 50%;
            animation: particle-float 20s infinite linear;
        }

        @keyframes particle-float {
            0% { transform: translateY(100vh) translateX(0) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100px) translateX(100px) rotate(180deg); opacity: 0; }
        }

        /* Container principal */
        .container {
            display: grid;
            grid-template-columns: 1fr 1.2fr;
            min-height: 100vh;
        }

        /* Lado esquerdo - Hero Section */
        .hero-section {
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.1) 0%, rgba(16, 185, 129, 0.1) 100%);
            padding: 3rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 500px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .logo-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            color: white;
            box-shadow: 0 10px 25px rgba(99, 102, 241, 0.3);
        }

        .logo-text {
            font-size: 2rem;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-title {
            font-size: 3.2rem;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            background: linear-gradient(135deg, var(--light) 0%, #cbd5e1 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-subtitle {
            font-size: 1.3rem;
            color: var(--text-light);
            margin-bottom: 3rem;
            line-height: 1.6;
        }

        .features {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .feature {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1.2rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .feature:hover {
            transform: translateX(10px);
            background: rgba(255, 255, 255, 0.08);
            border-color: rgba(99, 102, 241, 0.3);
        }

        .feature-icon {
            width: 45px;
            height: 45px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            color: white;
        }

        .feature-text {
            font-weight: 500;
            font-size: 1.1rem;
        }

        /* Lado direito - Formulário */
        .form-section {
            background: rgba(15, 23, 42, 0.8);
            backdrop-filter: blur(20px);
            border-left: 1px solid rgba(255, 255, 255, 0.1);
            padding: 3rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .form-container {
            max-width: 500px;
            margin: 0 auto;
            width: 100%;
        }

        .form-header {
            text-align: center;
            margin-bottom: 3rem;
        }

        .form-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .form-subtitle {
            color: var(--text-light);
            font-size: 1.1rem;
        }

        /* Estilos do formulário */
        .form-group {
            margin-bottom: 1.8rem;
            position: relative;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.2rem;
        }

        label {
            display: block;
            margin-bottom: 0.7rem;
            font-weight: 600;
            color: var(--light);
            font-size: 0.95rem;
        }

        .input-group {
            position: relative;
        }

        input, select, textarea {
            width: 100%;
            padding: 1.2rem 1.2rem 1.2rem 3.2rem;
            background: rgba(30, 41, 59, 0.6);
            border: 2px solid rgba(255, 255, 255, 0.1);
            border-radius: 12px;
            color: var(--light);
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--primary);
            background: rgba(30, 41, 59, 0.8);
            box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.2);
        }

        .input-icon {
            position: absolute;
            left: 1.2rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-light);
            font-size: 1.1rem;
        }

        textarea {
            padding: 1.2rem;
            resize: vertical;
            min-height: 120px;
        }

        .checkbox-group {
            display: flex;
            align-items: flex-start;
            gap: 0.8rem;
            margin: 2rem 0;
        }

        .checkbox-group input {
            width: auto;
            margin-top: 0.3rem;
        }

        .checkbox-group label {
            font-weight: normal;
            font-size: 0.9rem;
            line-height: 1.5;
        }

        .btn-submit {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 1.3rem 2.5rem;
            border-radius: 12px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.8rem;
            width: 100%;
            box-shadow: 0 10px 25px rgba(99, 102, 241, 0.3);
        }

        .btn-submit:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 30px rgba(99, 102, 241, 0.4);
        }

        .btn-submit:active {
            transform: translateY(0);
        }

        /* Tela de sucesso */
        .success-screen {
            display: none;
            text-align: center;
            padding: 4rem 2rem;
            background: rgba(15, 23, 42, 0.9);
            border-radius: 20px;
            border: 1px solid rgba(16, 185, 129, 0.3);
            animation: fadeIn 0.5s ease;
        }

        .success-screen.active {
            display: block;
        }

        .success-icon {
            font-size: 5rem;
            color: var(--success);
            margin-bottom: 2rem;
            animation: bounce 1s infinite alternate;
        }

        @keyframes bounce {
            from { transform: translateY(0); }
            to { transform: translateY(-10px); }
        }

        .success-title {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            background: linear-gradient(135deg, var(--success), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .success-text {
            color: var(--text-light);
            margin-bottom: 2.5rem;
            font-size: 1.1rem;
            line-height: 1.6;
        }

        .btn-new {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 10px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-new:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(245, 158, 11, 0.3);
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Elementos flutuantes decorativos */
        .floating-elements {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .floating-element {
            position: absolute;
            font-size: 2rem;
            opacity: 0.1;
            animation: float 15s infinite linear;
        }

        .float-1 { top: 10%; left: 10%; animation-delay: 0s; }
        .float-2 { top: 70%; left: 80%; animation-delay: 3s; }
        .float-3 { top: 40%; left: 85%; animation-delay: 6s; }
        .float-4 { top: 80%; left: 15%; animation-delay: 9s; }
        .float-5 { top: 20%; left: 75%; animation-delay: 12s; }

        @keyframes float {
            0% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(15px, 20px) rotate(5deg); }
            50% { transform: translate(30px, 10px) rotate(0deg); }
            75% { transform: translate(15px, -15px) rotate(-5deg); }
            100% { transform: translate(0, 0) rotate(0deg); }
        }

        /* Responsividade */
        @media (max-width: 968px) {
            .container {
                grid-template-columns: 1fr;
            }
            
            .hero-section {
                padding: 2rem;
            }
            
            .form-section {
                border-left: none;
                border-top: 1px solid rgba(255, 255, 255, 0.1);
            }
            
            .hero-title {
                font-size: 2.5rem;
            }
        }

        @media (max-width: 640px) {
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .hero-title {
                font-size: 2rem;
            }
            
            .form-title {
                font-size: 2rem;
            }
            
            .form-section, .hero-section {
                padding: 1.5rem;
            }
        }

        /* Animações de entrada */
        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .hero-content {
            animation: slideInLeft 0.8s ease forwards;
        }

        .form-container {
            animation: slideInRight 0.8s ease forwards;
        }
    </style>
</head>
<body>
    <!-- Partículas animadas -->
    <div class="particles" id="particles-container"></div>

    <div class="container">
        <!-- Lado Esquerdo - Conteúdo -->
        <div class="hero-section">
            <div class="floating-elements">
                <div class="floating-element float-1">💼</div>
                <div class="floating-element float-2">🚀</div>
                <div class="floating-element float-3">🌟</div>
                <div class="floating-element float-4">📈</div>
                <div class="floating-element float-5">🎯</div>
            </div>
            
            <div class="hero-content">
                <div class="logo">
                    <div class="logo-icon">
                        <i class="fas fa-handshake"></i>
                    </div>
                    <div class="logo-text">ConectaOportunidades</div>
                </div>
                
                <h1 class="hero-title">
                    Conectamos você às melhores oportunidades de trabalho
                </h1>
                
                <p class="hero-subtitle">
                    Cadastre-se gratuitamente e tenha acesso a vagas exclusivas de empresas que valorizam talentos como o seu.
                </p>
                
                <div class="features">
                    <div class="feature">
                        <div class="feature-icon">
                            <i class="fas fa-briefcase"></i>
                        </div>
                        <div class="feature-text">Oportunidades reais de emprego</div>
                    </div>
                    
                    <div class="feature">
                        <div class="feature-icon">
                            <i class="fas fa-graduation-cap"></i>
                        </div>
                        <div class="feature-text">Capacitação profissional gratuita</div>
                    </div>
                    
                    <div class="feature">
                        <div class="feature-icon">
                            <i class="fas fa-users"></i>
                        </div>
                        <div class="feature-text">Acompanhamento personalizado</div>
                    </div>
                    
                    <div class="feature">
                        <div class="feature-icon">
                            <i class="fas fa-chart-line"></i>
                        </div>
                        <div class="feature-text">Crescimento profissional garantido</div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Lado Direito - Formulário -->
        <div class="form-section">
            <div class="form-container">
                <div id="form-content">
                    <div class="form-header">
                        <h2 class="form-title">Cadastre-se Agora</h2>
                        <p class="form-subtitle">Preencha seus dados e dê o primeiro passo para uma nova carreira</p>
                    </div>
                    
                    <form id="registration-form">
                        <div class="form-row">
                            <div class="form-group">
                                <label for="nome">Nome Completo</label>
                                <div class="input-group">
                                    <i class="fas fa-user input-icon"></i>
                                    <input type="text" id="nome" name="nome" placeholder="Seu nome completo" required>
                                </div>
                            </div>
                            
                            <div class="form-group">
                                <label for="email">E-mail</label>
                                <div class="input-group">
                                    <i class="fas fa-envelope input-icon"></i>
                                    <input type="email" id="email" name="email" placeholder="seu@email.com" required>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="telefone">Telefone</label>
                                <div class="input-group">
                                    <i class="fas fa-phone input-icon"></i>
                                    <input type="tel" id="telefone" name="telefone" placeholder="(11) 99999-9999" required>
                                </div>
                            </div>
                            
                            <div class="form-group">
                                <label for="cidade">Cidade</label>
                                <div class="input-group">
                                    <i class="fas fa-city input-icon"></i>
                                    <input type="text" id="cidade" name="cidade" placeholder="Sua cidade" required>
                                </div>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="situacao">Situação Atual</label>
                            <div class="input-group">
                                <i class="fas fa-user-tie input-icon"></i>
                                <select id="situacao" name="situacao" required>
                                    <option value="">Selecione sua situação</option>
                                    <option value="desempregado">Desempregado(a)</option>
                                    <option value="primeiro-emprego">Buscando primeiro emprego</option>
                                    <option value="subemprego">Trabalho informal</option>
                                    <option value="transicao">Em transição de carreira</option>
                                    <option value="outro">Outra situação</option>
                                </select>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="habilidades">Habilidades e Experiências</label>
                            <textarea id="habilidades" name="habilidades" placeholder="Descreva suas habilidades, experiências profissionais, cursos realizados..." required></textarea>
                        </div>
                        
                        <div class="form-group">
                            <label for="interesses">Áreas de Interesse</label>
                            <textarea id="interesses" name="interesses" placeholder="Quais tipos de trabalho você tem interesse? (ex: atendimento, vendas, administrativo...)"></textarea>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="disponibilidade">Disponibilidade</label>
                                <div class="input-group">
                                    <i class="fas fa-clock input-icon"></i>
                                    <select id="disponibilidade" name="disponibilidade" required>
                                        <option value="">Selecione</option>
                                        <option value="integral">Tempo Integral</option>
                                        <option value="meio-periodo">Meio Período</option>
                                        <option value="flexivel">Horário Flexível</option>
                                        <option value="fins-semana">Fins de Semana</option>
                                    </select>
                                </div>
                            </div>
                            
                            <div class="form-group">
                                <label for="experiencia">Experiência Profissional</label>
                                <div class="input-group">
                                    <i class="fas fa-chart-line input-icon"></i>
                                    <select id="experiencia" name="experiencia" required>
                                        <option value="">Selecione</option>
                                        <option value="nenhuma">Nenhuma experiência</option>
                                        <option value="ate-1-ano">Até 1 ano</option>
                                        <option value="1-3-anos">1 a 3 anos</option>
                                        <option value="3-5-anos">3 a 5 anos</option>
                                        <option value="mais-5-anos">Mais de 5 anos</option>
                                    </select>
                                </div>
                            </div>
                        </div>
                        
                        <div class="checkbox-group">
                            <input type="checkbox" id="termos" name="termos" required>
                            <label for="termos">Concordo com os termos de uso e política de privacidade. Autorizo o contato para oportunidades de trabalho.</label>
                        </div>
                        
                        <button type="submit" class="btn-submit">
                            <i class="fas fa-paper-plane"></i>
                            Finalizar Cadastro
                        </button>
                    </form>
                </div>
                
                <!-- Tela de sucesso -->
                <div class="success-screen" id="success-screen">
                    <div class="success-icon">
                        <i class="fas fa-check-circle"></i>
                    </div>
                    <h2 class="success-title">Cadastro Realizado!</h2>
                    <p class="success-text">Seu cadastro foi recebido com sucesso. Nossa equipe entrará em contato em breve com oportunidades compatíveis com seu perfil.</p>
                    <button class="btn-new" onclick="resetForm()">
                        <i class="fas fa-plus"></i>
                        Fazer Novo Cadastro
                    </button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Criar partículas animadas
        function createParticles() {
            const container = document.getElementById('particles-container');
            const particleCount = 25;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Tamanho aleatório
                const size = Math.random() * 8 + 3;
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                
                // Posição inicial aleatória
                particle.style.left = `${Math.random() * 100}vw`;
                
                // Atraso de animação aleatório
                particle.style.animationDelay = `${Math.random() * 20}s`;
                
                // Duração aleatória
                particle.style.animationDuration = `${15 + Math.random() * 10}s`;
                
                container.appendChild(particle);
            }
        }

        // Processar formulário
        document.getElementById('registration-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Validação dos campos
            const camposObrigatorios = this.querySelectorAll('[required]');
            let valido = true;
            
            camposObrigatorios.forEach(campo => {
                if (!campo.value.trim()) {
                    valido = false;
                    campo.style.borderColor = '#ef4444';
                } else {
                    campo.style.borderColor = 'rgba(255, 255, 255, 0.1)';
                }
            });
            
            if (!valido) {
                alert('Por favor, preencha todos os campos obrigatórios.');
                return;
            }
            
            // Simular envio
            const btnSubmit = this.querySelector('.btn-submit');
            const originalText = btnSubmit.innerHTML;
            
            btnSubmit.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Enviando...';
            btnSubmit.disabled = true;
            
            setTimeout(() => {
                // Mostrar tela de sucesso
                document.getElementById('form-content').style.display = 'none';
                document.getElementById('success-screen').classList.add('active');
                
                // Aqui você pode adicionar código para enviar os dados para um servidor
                console.log('Dados do formulário:', coletarDadosFormulario());
                
            }, 2000);
        });
        
        function resetForm() {
            document.getElementById('registration-form').reset();
            document.getElementById('success-screen').classList.remove('active');
            document.getElementById('form-content').style.display = 'block';
            
            const btnSubmit = document.querySelector('.btn-submit');
            btnSubmit.innerHTML = '<i class="fas fa-paper-plane"></i> Finalizar Cadastro';
            btnSubmit.disabled = false;
        }
        
        function coletarDadosFormulario() {
            const formData = new FormData(document.getElementById('registration-form'));
            const dados = {};
            
            for (let [key, value] of formData.entries()) {
                dados[key] = value;
            }
            
            return dados;
        }

        // Inicialização
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
        });
    </script>
</body>
</html>
