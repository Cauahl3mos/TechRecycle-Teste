🌱 Tech-Recycle
Sistema web para incentivar o descarte correto de resíduos, com cadastro e login de usuários, funcionalidades de mapa e informações de reciclagem.
---


# 📦 Tech Recycle — Teste Unitário

## 📖 Introdução

Este repositório foi criado com o principal objetivo de demonstrar a aplicação de **testes unitários** em um projeto utilizando **Node.js** e **Jest**. O foco está no desenvolvimento e validação da função `passwordValidator`, que garante a segurança mínima exigida para senhas.

O projeto serve como um exemplo prático de como implementar e estruturar testes unitários, reforçando a importância das boas práticas de qualidade de software, garantindo que as funções desenvolvidas se comportem conforme o esperado.

---

## ✅ **1. O que é um Teste Unitário?**

É uma técnica de desenvolvimento de software onde testamos **unidades individuais de código** (geralmente funções ou métodos) para verificar se estão funcionando corretamente, de forma **isolada**.

**No nosso caso:**
→ A unidade é a função `passwordValidator(password)`.

---

## ✅ **2. Como estruturamos o teste no Tech Recycle**

### **2.1 Criamos a função `passwordValidator.js`**

Ela verifica se uma senha:

* Tem **no mínimo 8 caracteres**.
* Tem pelo menos **uma letra maiúscula**.
* Tem pelo menos **um número**.

**Exemplo:**

```javascript
function passwordValidator(password) {
    const minLength = 8;
    const hasUpperCase = /[A-Z]/.test(password);
    const hasNumber = /\d/.test(password);

    return password.length >= minLength && hasUpperCase && hasNumber;
}
```

**Se a senha for válida**, retorna `true`.
**Se for inválida**, retorna `false`.

---

### **2.2 Criamos o teste: `passwordValidator.test.js`**

Esse arquivo é onde escrevemos **os testes unitários**.

Usamos a ferramenta **Jest** para isso.
Cada `test()` descreve um cenário que queremos verificar.

**Exemplo:**

```javascript
test('Senha inválida: sem número', () => {
    expect(passwordValidator('SenhaFraca')).toBe(false);
});
```

→ Aqui testamos que uma senha **sem número** deve ser considerada **inválida**.

---

## ✅ **3. Como rodamos o teste?**

### **3.1 Instalamos o Jest:**

```bash
npm install jest --save-dev
```

---

### **3.2 Configuramos o `package.json`**:

Adicionamos este comando:

```json
"scripts": {
  "test": "jest"
}
```

Assim podemos rodar **`npm test`** no terminal.

---

### **3.3 Executamos o teste:**

```bash
npm test
```

O Jest lê automaticamente todos os arquivos `*.test.js` e executa os testes.

**O terminal mostrará:**

✅ Para cada teste que **passou**
❌ Se algum teste **falhou**

---

## ✅ **4. Por que é importante o Teste Unitário?**

* **Evita erros:** garante que funções simples estão funcionando antes mesmo de integrar ao sistema.
* **Facilita manutenção:** se alguém alterar o código, os testes vão alertar sobre possíveis quebras.
* **Automatiza a verificação:** com um comando (`npm test`), sabemos se está tudo funcionando.

---

## ✅ **5. Como ficou no Tech Recycle?**

* ✔️ Criamos a função de validação.
* ✔️ Criamos o arquivo de testes.
* ✔️ Configuramos o ambiente de testes.
* ✔️ Rodamos os testes no terminal com `npm test`.

---

## ✅ **6. Exemplo de saída no terminal:**

```
PASS  ./passwordValidator.test.js
✓ Senha válida: contém maiúscula, número e tem mais de 8 caracteres (10 ms)
✓ Senha inválida: menos de 8 caracteres (3 ms)
✓ Senha inválida: sem letra maiúscula (2 ms)
✓ Senha inválida: sem número (1 ms)

Test Suites: 1 passed, 1 total
Tests:       4 passed, 4 total
```
## 🛠️ Tecnologias e ferramentas utilizadas

- **Node.js** — ambiente de execução.
- **Jest** — biblioteca para realização de testes unitários.
- **NPM** — gerenciador de pacotes do Node.js.
- **Git** — para versionamento de código.

---
