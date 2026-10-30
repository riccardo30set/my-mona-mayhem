<!-- l10n-sync: source-file="03-agent-mode.md" -->
# Parte 3: Construção do jogo com fluxos de trabalho agênticos

---

Nesta parte, o Copilot passa do planejamento para a implementação. Em vez de escrever código linha por linha, você descreve o que quer e deixa o Copilot trabalhar nos arquivos necessários.

## Tarefa 1: Conecte a batalha

<!-- track:vscode:start -->
1. Mude para **Agent** no Copilot Chat.
2. Insira este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Volte ao fluxo de programação padrão do Copilot CLI (ou continue no modo autopilot se quiser que o Copilot prossiga até você pará-lo).
2. Se for útil, inclua o arquivo da página como contexto: `@src/pages/index.astro`.
3. Insira este prompt:
<!-- track:cli:end -->

   > Add client-side JavaScript to the battle page that:
   > 1. When the Battle button is clicked, gets both usernames from the inputs
   > 2. Validates both are filled (show error if not)
   > 3. Fetches both users' contribution data in parallel from our API
   > 4. Renders contribution graphs as colored grids — each day is a colored square using GitHub's color palette
   > 5. Shows a VS badge between the two users
   > 6. Displays username, total contributions, and date range for each user
   > 7. Handles loading states and errors
   > 8. Also triggers on Enter key in input fields.
   > 9. Simple UI for now that is already scaffolded.
   >
   > Use TypeScript interfaces for the contribution data structure.

<!-- track:vscode:start -->
3. Deixe o Agent Mode implementar as alterações em vários arquivos, incluindo `index.astro`.
4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI implementar as alterações em `src/pages/index.astro`.
5. Use `/diff` para revisar as alterações geradas e, em seguida, aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a batalha

> **⚠️ As alterações não apareceram?** Se a página de batalha não atualizar, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie com `npm run dev` e atualize o navegador.

1. Digite `octocat` e `torvalds` como os nomes de usuário e clique em **Battle**.
2. Você deverá ver os gráficos de contribuições dos dois usuários lado a lado, com grades coloridas.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle: deverá aparecer um erro de validação.
   - Digite um nome de usuário inválido: o aplicativo deverá exibir um erro da API.
4. Pressione **Enter** em qualquer campo: a batalha deverá começar como se você tivesse clicado no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver muito certo, envie comentários ao Copilot. Por exemplo:

- *"The contribution squares are too large, make them 12x12px"*
- *"Add a hover tooltip showing the date and contribution count"*
- *"The loading state needs a pulse animation"*

<!-- track:vscode:start -->
O Agent Mode gerencia naturalmente as alterações em vários arquivos e as iterações. Cada prompt de acompanhamento aproveita o contexto anterior, permitindo refinar a implementação sem começar do zero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada prompt de acompanhamento se baseia nos anteriores. Use `/session` ou `/context` para inspecionar o contexto que o Copilot está mantendo e `/review` após uma iteração maior para procurar erros ou oportunidades de melhoria.
<!-- track:cli:end -->

## Dicas para esta parte

- **Seja específico sobre o que você quer**: requisitos claros levam a resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot se desviar.
- **Revise as alterações antes de aceitá-las**: inspecionar o código gerado é mais rápido do que reescrevê-lo depois.
- **Teste o aplicativo após cada etapa de implementação** para localizar problemas desde cedo.

## ✅ Parte 3 concluída

Você aprendeu a:

- Usar o Copilot para **implementar alterações em vários arquivos**
- **Iterar nos resultados** com comentários específicos
- Seguir o **ciclo completo de uma funcionalidade**: implementação, revisão, testes e refinamento
