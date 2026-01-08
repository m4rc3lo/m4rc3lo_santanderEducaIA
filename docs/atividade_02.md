<!--
Arquivo: atividade_02.md
Cor padrão: #0786b4
-->

<h1 style="color:#0786b4; margin-bottom:0;">Atividade 02 — Mini‑jogo com entrada e saída (Portugol Studio UNIVALI)</h1>
<p style="margin-top:6px;">
<b>Tipo:</b> avaliativa e interativa · <b>Foco:</b> comandos de entrada e saída (I/O (input/output)) + decisão básica ·
<b>Contexto:</b> Design de Games (prototipação de regra e feedback ao jogador).
</p>

<hr style="border:0; border-top:1px solid #0786b4; opacity:0.35;"/>

<h2 style="color:#0786b4;">1) Objetivo de aprendizagem</h2>

Ao final da atividade, a pessoa estudante deve ser capaz de:

<ul>
  <li><b>Modelar</b> uma situação simples de jogo como <b>entrada → processamento → saída</b>;</li>
  <li><b>Implementar</b> leitura de dados (ex.: nome, moedas, escolha) e exibir feedback textual consistente;</li>
  <li><b>Explicar</b>, em poucas linhas, como a solução aplicou pelo menos <b>2 pilares de PC (pensamento computacional)</b> (ex.: decomposição, abstração, algoritmização).</li>
</ul>

<h2 style="color:#0786b4;">2) Enunciado</h2>

Você vai criar um <b>mini‑jogo textual</b> (protótipo) chamado <b>“Loja do Aventureiro”</b>.

O protótipo simula um momento comum em jogos: o(a) jogador(a) entra em uma loja, escolhe um item e recebe um retorno claro do sistema.

<b>Regras mínimas</b>:

<ol>
  <li>O programa deve <b>ler</b>:
    <ul>
      <li>nome do(a) jogador(a) (texto)</li>
      <li>quantidade inicial de moedas (inteiro)</li>
      <li>opção de item (inteiro: 1, 2 ou 3)</li>
    </ul>
  </li>
  <li>O programa deve <b>mostrar</b> um <b>menu</b> com 3 itens e seus preços (exemplo abaixo).</li>
  <li>O programa deve <b>calcular</b> se a pessoa pode comprar o item escolhido:
    <ul>
      <li>Se tiver moedas suficientes: confirmar compra e mostrar moedas restantes.</li>
      <li>Se não tiver: negar compra e mostrar quantas moedas faltaram.</li>
    </ul>
  </li>
  <li>O programa deve imprimir, no fim, um <b>resumo</b> (nome, item, saldo final).</li>
</ol>

<b>Menu sugerido</b> (você pode alterar nomes, mas mantenha 3 opções e preços):

<ul>
  <li>1) Poção de Cura — 12 moedas</li>
  <li>2) Escudo de Madeira — 20 moedas</li>
  <li>3) Chave Misteriosa — 7 moedas</li>
</ul>

<h2 style="color:#0786b4;">3) Entregáveis</h2>

<ul>
  <li><b>Arquivo do projeto</b> do Portugol Studio (.por ou equivalente) com o código funcional.</li>
  <li><b>Print</b> (captura de tela) do console/saída mostrando uma execução real.</li>
  <li><b>Mini‑explicação</b> (5–8 linhas) respondendo:
    <ul>
      <li>Quais entradas foram usadas e por quê?</li>
      <li>Quais saídas são essenciais para o(a) jogador(a) entender o que aconteceu?</li>
      <li>Quais 2 pilares de PC (pensamento computacional) você aplicou?</li>
    </ul>
  </li>
</ul>

<h2 style="color:#0786b4;">4) Critérios de qualidade esperados</h2>

<ul>
  <li><b>Clareza de I/O (entrada/saída)</b>: perguntas e mensagens fáceis de entender, sem ambiguidades.</li>
  <li><b>Corretude</b>: cálculos e condições corretos (compra aprovada/negada corretamente).</li>
  <li><b>Organização</b>: nomes de variáveis coerentes, comentários curtos quando necessário.</li>
  <li><b>Contexto de jogo</b>: feedback “com cara de jogo” (ex.: mensagem de compra, saldo, item escolhido).</li>
</ul>

<hr style="border:0; border-top:1px solid #0786b4; opacity:0.25;"/>

<h2 style="color:#0786b4;">5) Template de código (base)</h2>

<pre><code>// Atividade 02 — Loja do Aventureiro (I/O + decisão)
// Observação: adapte os comandos de entrada/saída ao Portugol Studio (UNIVALI).

programa
{
    funcao inicio()
    {
        cadeia nome
        inteiro moedas, opcao
        cadeia item
        inteiro preco, faltou, resto

        escreva("Digite seu nome: ")
        leia(nome)

        escreva("Quantas moedas você tem? ")
        leia(moedas)

        escreval("\n=== Loja do Aventureiro ===")
        escreval("1) Poção de Cura — 12 moedas")
        escreval("2) Escudo de Madeira — 20 moedas")
        escreval("3) Chave Misteriosa — 7 moedas")
        escreva("Escolha uma opção (1-3): ")
        leia(opcao)

        // Define item e preço a partir da escolha
        se (opcao == 1) {
            item = "Poção de Cura"
            preco = 12
        } senao se (opcao == 2) {
            item = "Escudo de Madeira"
            preco = 20
        } senao se (opcao == 3) {
            item = "Chave Misteriosa"
            preco = 7
        } senao {
            escreval("\nOpção inválida. Encerrando.")
            retorne
        }

        escreval("\nJogador(a): " + nome)
        escreval("Item escolhido: " + item)
        escreval("Preço: " + preco + " moedas")
        escreval("Saldo inicial: " + moedas + " moedas")

        se (moedas &gt;= preco) {
            resto = moedas - preco
            escreval("\nCompra APROVADA! Você recebeu: " + item)
            escreval("Moedas restantes: " + resto)
        } senao {
            faltou = preco - moedas
            escreval("\nCompra NEGADA. Faltaram " + faltou + " moedas.")
            escreval("Moedas atuais: " + moedas)
        }

        escreval("\n=== Fim do protótipo ===")
    }
}
</code></pre>

<h2 style="color:#0786b4;">6) Extensões opcionais (vale bônus / “se quiser ir além”)</h2>

<ul>
  <li><b>Loop de compras</b>: permitir comprar novamente enquanto houver moedas (usando repetição).</li>
  <li><b>Desconto</b>: ler um cupom (texto) e aplicar 10% de desconto se o cupom for válido.</li>
  <li><b>Inventário simples</b>: após comprar, listar itens adquiridos (por exemplo, 2 compras no máximo).</li>
  <li><b>Balanceamento</b>: justificar preços (3–5 linhas) pensando em progressão e feedback ao jogador.</li>
</ul>

<hr style="border:0; border-top:1px solid #0786b4; opacity:0.25;"/>

<h2 style="color:#0786b4;">7) Checklist rápido de autoavaliação</h2>

<ul>
  <li>[ ] Eu li pelo menos 3 entradas (nome, moedas, opção).</li>
  <li>[ ] Eu imprimi um menu com 3 itens e preços.</li>
  <li>[ ] Eu tratei opção inválida.</li>
  <li>[ ] Eu calculei corretamente compra aprovada/negada.</li>
  <li>[ ] Eu mostrei um resumo final claro.</li>
  <li>[ ] Eu escrevi uma explicação curta citando 2 pilares de PC (pensamento computacional).</li>
</ul>
