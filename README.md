# 🎮 Jogo: Adivinhe o Número Secreto

## 📋 Descrição Geral
"Adivinhe o Número Secreto" é um jogo interativo desenvolvido como parte do programa ONE (Oracle Next Education) em parceria com a Alura. O objetivo do jogo é simples: o jogador deve adivinhar um número secreto gerado aleatoriamente entre 1 e 10. O jogo fornece dicas ao jogador, como "o número secreto é maior" ou "o número secreto é menor", até que ele acerte o número.

---

## 🎯 Funcionalidades
- **Geração de número secreto:** O número é gerado aleatoriamente e muda a cada reinício do jogo.
- **Feedback ao jogador:** O jogo indica se o número secreto é maior ou menor que o palpite.
- **Contador de tentativas:** O número de tentativas é exibido ao jogador ao final do jogo.
- **Opção de reiniciar:** Após acertar o número, o jogador pode reiniciar o jogo e tentar novamente.
- **Acessibilidade:** Utiliza a biblioteca `responsiveVoice` para feedback auditivo.

---

## 🛠️ Tecnologias Utilizadas
- ![JavaScript](https://camo.githubusercontent.com/2ed691285a3c5eec6c2b2cd2d2bc610a09e39dab92e69a5999a5d1a43b873c4b/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2d4a6176615363726970742d4637444631453f7374796c653d666c61742d737175617265266c6f676f3d6a617661736372697074266c6f676f436f6c6f723d626c61636b) **JavaScript:** Para implementar a lógica do jogo e a interatividade.
- **HTML:** Para a estruturação da interface do jogo.
- **CSS:** Para estilização básica.
- **responsiveVoice.js:** Biblioteca para fornecer suporte de áudio no jogo.

---

## 🧠 Conceitos Aplicados
- **Funções com retorno e parâmetros:** Utilizadas para modularizar a lógica, como gerar números aleatórios e exibir mensagens.
- **Listas:** Implementadas para controlar os números já sorteados e evitar repetição.
- **Lógica de programação:** Estruturas condicionais e loops foram usados para gerenciar a interação com o jogador.
- **Manipulação do DOM:** Atualização dinâmica dos elementos da página com base na interação do jogador.

---

## 🎮 Como Jogar
1. Escolha um número entre 1 e 10 no campo de entrada.
2. Clique no botão de envio para verificar sua tentativa.
3. O jogo informará se o número secreto é maior ou menor que o escolhido.
4. Continue tentando até acertar o número secreto!
5. Após acertar, clique no botão "Reiniciar" para jogar novamente.

---

## 📂 Estrutura do Código
1. **Geração do número secreto:**
   ```javascript
   function gerarNumeroAleatorio() {
       let numeroEscolhido = parseInt(Math.random() * numeroLimite + 1);
       // Controle para evitar repetição de números
       if (listaDeNumerosSorteados.includes(numeroEscolhido)) {
           return gerarNumeroAleatorio();
       } else {
           listaDeNumerosSorteados.push(numeroEscolhido);
           return numeroEscolhido;
       }
   }
   ```

2. **Verificação do chute:**
   ```javascript
   function verificarChute() {
       let chute = document.querySelector('input').value;
       if (chute == numeroSecreto) {
           exibirTextoNaTela('h1', 'Acertou!');
       } else if (chute > numeroSecreto) {
           exibirTextoNaTela('p', 'O número secreto é menor');
       } else {
           exibirTextoNaTela('p', 'O número secreto é maior');
       }
       tentativas++;
   }
   ```

3. **Reinício do jogo:**
   ```javascript
   function reiniciarJogo() {
       numeroSecreto = gerarNumeroAleatorio();
       tentativas = 1;
       exibirMensagemInicial();
   }
   ```

---

## 🚀 Como Executar o Projeto
1. Baixe ou clone este repositório.
2. Abra o arquivo `index.html` em um navegador moderno.
3. Certifique-se de ter conexão com a internet para carregar a biblioteca `responsiveVoice.js`.
4. Divirta-se jogando!

---

## 🔮 Próximos Passos
- Melhorar o design da interface do jogo.
- Adicionar níveis de dificuldade com diferentes intervalos de números secretos.
- Criar um histórico das tentativas.
- Internacionalizar o jogo para suportar outros idiomas.

---

## ✍️ Créditos
Este projeto foi desenvolvido por [Seu Nome], como parte do programa Oracle Next Education em parceria com a Alura.

---

## 📜 Licença
Este projeto está licenciado sob a licença MIT.

