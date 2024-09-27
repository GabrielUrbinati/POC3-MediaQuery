# POC3-MediaQuery
Prova de Conceito sobre Aplicações de Media Query em diferentes telas e orientação.
# Exemplo de Breakpoints com Media Queries

Este projeto é um exemplo de como utilizar **media queries** no CSS para criar layouts responsivos e adaptáveis para diferentes tamanhos de dispositivos, além de estilos específicos para impressão e modos de orientação de tela (landscape e portrait).

## Funcionalidades

O projeto implementa **breakpoints** para diversos cenários, tais como:

- **Estilos para dispositivos móveis (smartphones)**
- **Estilos para tablets**
- **Estilos para desktops**
- **Estilos específicos para impressão**
- **Detecção de orientação (landscape e portrait)**

## Como Funciona

### Estrutura do Projeto

- `index.html`: Contém a estrutura HTML principal, incluindo o cabeçalho, menu de navegação, galeria de imagens e rodapé.
- `style.css`: Arquivo de estilos com os **media queries** que adaptam o layout conforme o tamanho da tela, a orientação do dispositivo e o contexto de impressão.

### Requisitos Implementados

#### 1. Media Query para Impressão

O projeto inclui uma **media query para impressão** que reorganiza o layout para otimizar a impressão. Quando o usuário imprime a página, os seguintes ajustes são feitos:

- O menu de navegação e o rodapé são ocultados.
- O conteúdo principal é organizado em **duas colunas**, economizando espaço no papel.
- O tamanho da fonte é ajustado para melhorar a legibilidade na página impressa.

**CSS:**
```css
@media print {
    body {
        font-size: 12pt;
        line-height: 1.5;
        color: black;
    }

    nav, footer, .no-print {
        display: none;
    }

    main {
        columns: 2;
        column-gap: 20px;
    }
}
```

#### 2. Media Queries para Diferentes Tamanhos de Dispositivos

Foram implementadas **media queries** específicas para três tipos de dispositivos: **smartphones**, **tablets** e **desktops**. Cada uma adapta o layout para garantir a melhor experiência visual em cada tipo de tela.

- **Smartphones (max-width: 600px)**:
    - O menu de navegação é reorganizado para uma coluna.
    - A galeria de imagens passa a ocupar uma única coluna.
    - As imagens da galeria recebem altura fixa para melhor visualização.

**CSS:**
```css
@media (max-width: 600px) {
    nav ul {
        flex-direction: column;
        align-items: center;
    }

    .gallery {
        grid-template-columns: 1fr;
    }

    .gallery img {
        height: 150px;
        margin-bottom: 10px;
    }
}
```
- **Tablets (min-width: 601px e max-width: 900px)**:
    - A galeria de imagens é organizada em duas colunas, utilizando melhor o espaço disponível.

**CSS:**
```css
@media (min-width: 601px) and (max-width: 900px) {
    .gallery {
        grid-template-columns: repeat(2, 1fr);
    }
}
```
- **Desktops (min-width: 901px)**:
    - A galeria de imagens é exibida em três colunas, aproveitando a largura adicional das telas maiores.

**CSS:**
```css
@media (min-width: 901px) {
    .gallery {
        grid-template-columns: repeat(3, 1fr);
    }
}
```
#### 3. Detecção de Orientação (Landscape e Portrait)

O layout também responde à **orientação do dispositivo**, ou seja, a página detecta se o dispositivo está em modo **landscape** ou **portrait**, e ajusta a disposição do conteúdo.

- Quando o dispositivo está em **landscape**, o conteúdo principal (`main`) é reorganizado em uma linha (layout horizontal).

**CSS:**
```css
@media (orientation: landscape) {
    main {
        display: flex;
        flex-direction: row;
    }
}
```
## Como Usar

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git


2. Abra o arquivo index.html em seu navegador.

3. Inspecione o layout em diferentes dispositivos (ou use o modo de desenvolvimento do navegador para simular diferentes tamanhos de tela).

Para isso, no navegador (Google Chrome ou Firefox, por exemplo), pressione F12 para abrir as ferramentas de desenvolvedor e selecione a aba de Responsividade (ícone de dispositivos móveis).
Verifique como o layout se adapta a diferentes larguras de tela (smartphones, tablets e desktops).

####Para testar a funcionalidade de impressão:

Pressione Ctrl + P (Windows) ou Cmd + P (Mac).
Visualize como a página é ajustada para o formato de impressão, com o menu e rodapé ocultos e o conteúdo distribuído em colunas.

####Tecnologias Utilizadas

HTML5: Marcações semânticas para estruturar a página.
CSS3: Estilos e media queries para responsividade e adaptação ao contexto de impressão.

