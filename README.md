# ArtPixel
Simple, I created it based on a GitHub post within LinkedIn, thinking that maybe GitHub and/or associates and partners have a job or demand for me. Created on 10/1/25, the day I resigned from a job where the owners themselves do not want to improve or change the company's processes, services, etc., and the company's organization, culture, and demands are really terrible.
Este projeto implementa uma **interface retro em estilo CRT com pixel art animada**.  
A animação é renderizada em um `<canvas>` a partir de quadros (`frames`) descritos em JSON, permitindo criar animações personalizadas em estilo **pixel art**.

---

## 🚀 Tecnologias Utilizadas

- **HTML5** – Estrutura da página
- **CSS3** – Estilização com efeitos retro (CRT glow, scanlines, moldura animada)
- **JavaScript (ES6)** – Renderização da animação em canvas
- **JSON** – Armazenamento dos frames da pixel art
- **Canvas API** – Desenho eficiente de pixels no navegador

---

## 📂 Estrutura do Projeto

```
/
├── index.html                  # Arquivo principal da aplicação
├── pixelart_frames_72x56_full.json # Arquivo contendo os frames da animação
├── /assets                     # (opcional) Pasta para outros recursos
└── README.md                   # Documentação do projeto
```

---

## 📖 Funcionamento Técnico

### 1. Estrutura HTML
- O HTML define uma **moldura retro CRT** contendo:
  - `canvas` (`id="arte"`) onde a animação é desenhada.
  - Efeitos visuais como scanlines, bordas luminosas e tremor da tela.
  - Um **rodapé de status** com texto animado `"Pensando..."`.

### 2. Estilo CSS
- Uso de **variáveis CSS** (`:root`) para definir paleta de cores.
- Efeitos de:
  - **Glow CRT** (`box-shadow`, `drop-shadow`).
  - **Scanlines** (`repeating-linear-gradient`).
  - **Flicker** (`@keyframes tremor`).
  - **Entrada suave** da interface (`@keyframes entrada`).

### 3. Paleta de Cores
A paleta é definida em um objeto JavaScript que mapeia símbolos para cores:

```js
const paletaCores = {
  'k': '#0b0b10', // preto
  'P': '#b66bff', // roxo claro
  'p': '#a455f7', // roxo escuro
  'B': '#77c7ff', // azul claro
  'b': '#5bb1ef', // azul escuro
  'G': '#8ef1a0', // verde
  'W': '#ffffff', // branco
  '.': null       // transparente
};
```

Cada quadro da animação é representado como uma **matriz de caracteres**, em que cada símbolo corresponde a uma cor.

### 4. Animação
- O script carrega `pixelart_frames_72x56_full.json` via **fetch API**.
- A função `iniciarAnimacao` controla o ciclo:
  - `desenhar()` – Renderiza um quadro no canvas.
  - `requestAnimationFrame` – Sincroniza os frames na taxa configurada (`FPS = 30`).
  - Ajuste automático ao `resize` da janela.

---

## 🖼️ Como Criar Novos Frames

Cada frame é um **array bidimensional** no JSON:

```json
[
  ["k","k","k","B","B"],
  ["k","P","P","B","k"],
  ["k","p","p","B","k"],
  ["k","k","k","k","k"]
]
```

- Cada string é um símbolo da paleta (`k`, `P`, `p`, `B`, etc.).
- O canvas é redimensionado automaticamente para a largura/altura do frame.

---

## ▶️ Como Executar

1. Clone o repositório ou copie os arquivos:
   ```bash
   git clone https://github.com/seuusuario/artpixel.git
   cd artpixel
   ```

2. Certifique-se de que `index.html` e `pixelart_frames_72x56_full.json` estão na mesma pasta.

3. Abra o arquivo `index.html` no navegador.

---

## ⚙️ Configurações Opcionais

- **FPS**: Pode ser ajustado na constante do script:
  ```js
  const FPS = 30; // Altere para 60 para animação mais fluida
  ```

- **Cores**: Adicione ou modifique símbolos no objeto `paletaCores`.

- **Tamanho**: Alterando o JSON de frames, a resolução da pixel art também é ajustada automaticamente.

---

## 📌 Acessibilidade
- O `role="img"` e `aria-label` foram adicionados para leitores de tela.
- O `canvas` tem `aria-hidden="true"` para não atrapalhar a navegação assistiva.

---

## ✨ Autor
Projeto desenvolvido por **Gustavo Lima G (AKIKO_YUUKI)**.  
