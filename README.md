# 🚀 Guia Completo – Primeira Aula de Next.js (Iniciantes)

---

# 1️⃣ O que é Next.js?

Next.js é um framework baseado em React para criação de aplicações web modernas.

Ele resolve automaticamente:

- Estrutura do projeto
- Sistema de rotas
- Otimização de performance
- Renderização no servidor (SSR)
- Organização de páginas

---

## ✅ Vantagens

- Roteamento automático por pastas
- Melhor SEO
- Suporte a SSR e CSR
- Organização profissional de projeto
- Fácil deploy

## ❌ Desvantagens

- Pode parecer complexo no início
- Algumas decisões estruturais já vêm definidas

---

# 2️⃣ SSR vs CSR

## 🔵 CSR (Client Side Rendering)

Renderização no navegador.

Como funciona:

1. O servidor envia um HTML simples
2. O JavaScript carrega
3. O React monta a página no navegador

✔ Ideal para sistemas internos
✔ Aplicações altamente interativas

---

## 🟢 SSR (Server Side Rendering)

Renderização no servidor.

Como funciona:

1. O usuário acessa a página
2. O servidor monta o HTML completo
3. O navegador recebe a página pronta

✔ Melhor para SEO
✔ Melhor para sites públicos

---

# 3️⃣ Criando o Projeto

No terminal:

```bash
npx create-next-app@latest
```

### Respostas recomendadas para iniciantes:

- TypeScript → No
- ESLint → Yes
- Tailwind → Yes
- App Router → Yes
- src directory → Opcional

Depois executar:

```bash
npm run dev
```

Abrir no navegador:

```
http://localhost:3000
```

---

# 4️⃣ Criando uma Nova Rota

Criar a pasta:

```
app/sobre/page.js
```

Código:

```javascript
export default function Sobre() {
  return <h1>Sobre</h1>;
}
```

A rota será automaticamente:

```
http://localhost:3000/sobre
```

Next cria rotas automaticamente baseado nas pastas.

---

# 5️⃣ Criando Componente Header

Criar:

```
components/Header.js
```

```javascript
export default function Header() {
  return (
    <header className="bg-black text-white p-4 flex justify-between items-center">
      <h1 className="text-xl font-bold">Minha Aplicação</h1>
      <nav className="space-x-4">
        <a href="/">Home</a>
        <a href="/sobre">Sobre</a>
      </nav>
    </header>
  );
}
```

Importar na página Home:

```javascript
import Header from "@/components/Header";

export default function Home() {
  return (
    <>
      <Header />
      <h1>Home</h1>
    </>
  );
}
```

Repetir na página Sobre.

---

# 6️⃣ Criando Componente Footer

Criar:

```
components/Footer.js
```

```javascript
export default function Footer() {
  return (
    <footer className="bg-gray-900 text-white text-center p-4 mt-10">
      <p>© 2026 - Minha Aplicação</p>
    </footer>
  );
}
```

Importar nas páginas.

---

# 7️⃣ Diferença entre class e className

HTML usa:

```html
<div class="card"></div>
```

React / Next usa:

```javascript
<div className="card"></div>
```

Motivo:

"class" é palavra reservada do JavaScript.

Sempre usar className dentro do React.

---

# 8️⃣ Principais Classes do Tailwind

## 🎨 Cores

- bg-blue-500 → fundo azul
- bg-gray-200 → fundo cinza claro
- text-white → texto branco
- text-gray-800 → texto escuro

---

## 📦 Espaçamento

- p-4 → padding
- px-4 → padding horizontal
- py-2 → padding vertical
- m-4 → margin
- mt-4 → margin superior
- mb-4 → margin inferior

---

## 🔤 Texto

- text-xl → texto grande
- text-3xl → texto muito grande
- font-bold → negrito
- text-center → centraliza texto

---

## 📐 Tamanho

- w-full → largura total
- h-48 → altura fixa
- min-h-screen → altura mínima da tela

---

## 🔲 Bordas e Sombra

- rounded → borda arredondada
- rounded-lg → borda maior
- border → adiciona borda
- shadow-md → sombra média

---

# 9️⃣ Alinhamento e Posicionamento

## 🔹 Flexbox

- flex → ativa flex
- flex-col → organiza em coluna
- justify-center → centraliza horizontal
- justify-between → espaço entre elementos
- items-center → centraliza vertical
- flex-1 → faz o elemento crescer e ocupar o espaço disponível

Exemplo:

```javascript
<div className="flex justify-center items-center h-screen">
  <div>Centralizado</div>
</div>
```

---

## 🔹 Grid

- grid → ativa grid
- grid-cols-1 → 1 coluna
- grid-cols-2 → 2 colunas
- grid-cols-3 → 3 colunas
- gap-4 → espaçamento entre itens

Exemplo:

```javascript
<div className="grid grid-cols-3 gap-4">
  <div className="bg-gray-200 p-4">1</div>
  <div className="bg-gray-200 p-4">2</div>
  <div className="bg-gray-200 p-4">3</div>
</div>
```

---

# 🔟 Estrutura Profissional: Header no topo e Footer no final

Objetivo:

- Header sempre no topo
- Footer sempre no final da página
- Sem espaço sobrando abaixo
- Sem scroll horizontal

## 📁 layout.js

```javascript
export default function RootLayout({ children }) {
  return (
    <html>
      <body className="min-h-screen flex flex-col overflow-x-hidden">
        <Header />

        <main className="flex-1">{children}</main>

        <Footer />
      </body>
    </html>
  );
}
```

### 🔎 Explicação das classes usadas

- min-h-screen → ocupa no mínimo 100% da altura da tela
- flex flex-col → organiza elementos em coluna
- flex-1 → faz o conteúdo principal crescer e empurrar o footer
- overflow-x-hidden → remove scroll horizontal

---

## ⚠️ Evitar scroll horizontal

Evite usar:

```javascript
<div className="w-screen">
```

Prefira:

```javascript
<div className="w-full">
```

---

## 📌 Header fixo (opcional)

Se quiser fixar no topo:

```javascript
<header className="fixed top-0 w-full bg-black text-white p-4">
```

Adicionar espaçamento no main:

```javascript
<main className="flex-1 pt-16">
```

---


# 🎯 Objetivos Finais da Aula

Ao concluir esta aula, você deve:

- Entender o que é Next.js
- Saber criar um projeto
- Criar novas rotas
- Criar componentes reutilizáveis
- Entender className
- Usar Tailwind para estilizar
- Alinhar e posicionar elementos corretamente
- Montar estrutura profissional de página

---

📌 Esta é a base estrutural para evoluir para projetos maiores.
