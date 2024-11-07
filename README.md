# Responsive Web Design com HTML e CSS

## 1. Introdução ao Design Responsivo

O design responsivo é uma abordagem que garante que um site se adapte a diferentes tamanhos de tela, proporcionando uma experiência consistente em qualquer dispositivo. Com o crescimento do acesso mobile à internet, ter um site responsivo deixou de ser um diferencial para se tornar uma necessidade.

### Por que é importante?
- 📱 Mais de 50% do tráfego web vem de dispositivos móveis
- 🔍 Google prioriza sites mobile-friendly no ranking
- 💰 Melhor experiência do usuário = Maior taxa de conversão
- 🌐 Manutenção mais eficiente (um único código para todos os dispositivos)

## 2. Conceito Mobile First

Mobile First é uma estratégia de desenvolvimento onde começamos o design pensando primeiro nos dispositivos móveis e depois expandimos para telas maiores. 

### Vantagens do Mobile First:
- Foco no conteúdo essencial
- Performance otimizada
- Processo de desenvolvimento mais organizado
- Melhor experiência em dispositivos móveis

## 3. Elementos Fundamentais do Design Responsivo

### 3.1 Viewport Meta Tag
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### 3.2 Unidades Relativas
- `rem`: Relativa ao tamanho da fonte do elemento root
- `em`: Relativa ao tamanho da fonte do elemento pai
- `vw`: Relativa à largura da viewport
- `vh`: Relativa à altura da viewport
- `%`: Relativa ao elemento pai

### 3.3 Media Queries
```css
/* Mobile First - Começamos com estilos base para mobile */
.container {
    width: 100%;
    padding: 15px;
}

/* Tablet (768px e acima) */
@media screen and (min-width: 768px) {
    .container {
        width: 750px;
        margin: 0 auto;
    }
}

/* Desktop (992px e acima) */
@media screen and (min-width: 992px) {
    .container {
        width: 970px;
    }
}
```

## 4. Exemplo Prático

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Site Responsivo</title>
    <style>
        /* Reset básico */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Estilos base (mobile) */
        .header {
            background: #333;
            color: white;
            padding: 1rem;
            text-align: center;
        }

        .nav {
            background: #f4f4f4;
            padding: 1rem;
        }

        .nav-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .main-content {
            padding: 1rem;
        }

        .card-grid {
            display: grid;
            gap: 1rem;
            grid-template-columns: 1fr; /* Uma coluna no mobile */
        }

        .card {
            background: #f9f9f9;
            padding: 1rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        /* Tablet */
        @media screen and (min-width: 768px) {
            .nav-list {
                flex-direction: row;
                justify-content: center;
            }

            .card-grid {
                grid-template-columns: repeat(2, 1fr); /* Duas colunas */
            }
        }

        /* Desktop */
        @media screen and (min-width: 992px) {
            .container {
                max-width: 1200px;
                margin: 0 auto;
            }

            .card-grid {
                grid-template-columns: repeat(3, 1fr); /* Três colunas */
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Meu Site Responsivo</h1>
    </header>

    <nav class="nav">
        <ul class="nav-list">
            <li><a href="#">Home</a></li>
            <li><a href="#">Produtos</a></li>
            <li><a href="#">Sobre</a></li>
            <li><a href="#">Contato</a></li>
        </ul>
    </nav>

    <main class="main-content">
        <div class="card-grid">
            <div class="card">
                <h2>Card 1</h2>
                <p>Conteúdo do card 1</p>
            </div>
            <div class="card">
                <h2>Card 2</h2>
                <p>Conteúdo do card 2</p>
            </div>
            <div class="card">
                <h2>Card 3</h2>
                <p>Conteúdo do card 3</p>
            </div>
        </div>
    </main>
</body>
</html>
```

## 5. Boas Práticas

1. Sempre comece pelo mobile (Mobile First)
2. Use unidades relativas (rem, em, %, vw, vh)
3. Evite larguras fixas
4. Teste em múltiplos dispositivos
5. Mantenha o código organizado
6. Use breakpoints padrão:
   - Mobile: < 768px
   - Tablet: 768px - 991px
   - Desktop: ≥ 992px

## 6. Desafio Prático

### Objetivo
Criar uma landing page responsiva para uma loja de café.

### Requisitos:
1. Header com logo e menu de navegação
   - Menu deve virar hamburger menu em mobile
2. Banner principal com imagem de fundo
   - Texto deve ser legível em todas as resoluções
3. Seção de produtos
   - 1 coluna em mobile
   - 2 colunas em tablet
   - 3 colunas em desktop
4. Formulário de contato
   - Campos devem ocupar 100% da largura em mobile
   - Layout de duas colunas em desktop
5. Footer com informações de contato e redes sociais

### Breakpoints a serem utilizados:
- Mobile: até 767px
- Tablet: 768px a 991px
- Desktop: 992px e acima

### Bônus:
- Implementar animações suaves nas transições
- Adicionar um mapa responsivo
- Criar um menu hamburger funcional com JavaScript

## 7. Recursos Adicionais

Para aprofundar seus conhecimentos:
- [MDN Web Docs - Responsive Design](https://developer.mozilla.org/pt-BR/docs/Learn/CSS/CSS_layout/Responsive_Design)
- [CSS-Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS-Tricks - A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
