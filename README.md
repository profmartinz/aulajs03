# ⚡ Aula 03: Manipulação de Inputs, Tratamento de Strings e Exibição no DOM

## Aula
**Aula 03 - Inputs, Trim, innerText e Experiência do Usuário (UX)**

---

## Conteúdo da Aula

Nesta aula, avançamos no desenvolvimento web tratando da **captura, manipulação e exibição de dados de entrada** em tempo real[cite: 4]. Aprendemos como ler dados de campos `<input>`, realizar a sanitização de dados textuais (tratando espaços e padronizando caracteres) e refletir os resultados de forma dinâmica no HTML[cite: 4].

### 🎯 Tópicos Abordados:
1. **Seleção de Elementos de Formulário:** Mapeamento de `<input>`, botões e contêineres[cite: 4].
2. **Manipulação da Propriedade `.value`:** Leitura e redefinição de campos de texto[cite: 4].
3. **Melhoria de UX (Experiência do Usuário):** Suporte ao envio via tecla `Enter` com `keydown`[cite: 4].
4. **Sanitização de Strings:** Uso de `.trim()` para remoção de espaços e `.toLowerCase()` para padronização[cite: 4].
5. **Atualização do DOM:** Renderização de conteúdo com `.innerText`[cite: 4].
6. **Fluxo do Sistema:** Ciclo completo desde o clique/enter até a limpeza do campo de entrada[cite: 4].

### 🚀 Códigos e Exemplos Práticos:

#### 1. Seleção de Elementos e Evento de Clique
let input = document.querySelector("#entrada");
let botao = document.querySelector("#botao");
let resultado = document.querySelector("#resultado");

botao.addEventListener("click", executar);

#### 2. Melhoria de UX: Envio via Tecla Enter
input.addEventListener("keydown", function (e) {
  if (e.key === "Enter") {
    executar();
  }
});

#### 3. Função Principal: Captura, Tratamento, Exibição e Limpeza
function executar() {
  // Captura o valor digitado
  let texto = input.value;
  console.log("Texto original:", texto);

  // Tratamento de dados (Sanitização)
  texto = texto.trim();          // Remove espaços no início e fim
  texto = texto.toLowerCase();   // Converter para letras minúsculas
  console.log("Texto tratado:", texto);

  // Exibição na tela
  resultado.innerText = texto;

  // Limpeza do campo do input
  input.value = "";
}

---

## Estrutura do Projeto

Abaixo está a organização dos arquivos do projeto e o mapeamento dos elementos no DOM:

meu-projeto/
│-- index.html       # Estrutura HTML com input, botão e área de resposta
│-- style.css        # Estilização visual
└── script.js        # Lógica de captação, tratamento de texto e manipulação do DOM

### Mapeamento dos Elementos no HTML

| Identificador / Seletor | Elemento no HTML | Descrição / Função |
| :--- | :--- | :--- |
| `#entrada` | `<input>` | Campo de texto onde o usuário digita as mensagens |
| `#botao` | `<button>` | Dispara a função de processamento ao ser clicado |
| `#resultado` | `<div>` | Área de resposta onde o texto tratado é exibido |

---

## Como Executar o Projeto

1. **Estrutura dos Arquivos:**
   Certifique-se de que o arquivo `script.js` esteja importado no `index.html` (utilizando a tag `<script src="script.js" defer></script>`).

2. **Testando a Interação:**
   * Digite uma frase no campo `#entrada` adicionando espaços antes/depois e letras maiúsculas.
   * Pressione o botão **Enviar** ou tecle **Enter**.
   * Observe o resultado padronizado exibido na `<div>` `#resultado` e o campo de texto sendo resetado automaticamente.

3. **Verificação no Console:**
   * Abra a ferramenta de desenvolvedor (`F12`) e confira os logs do `console.log()` para comparar a string original e a versão higienizada.

---

👨‍🏫 **Professor:** MSc. Tiago Martins Ribeiro  
📚 **Disciplina:** Desenvolvimento Web para I.A.
