# Exemplo Completo de Integração

1. Comece importando todos os componentes base: `ChatContainer`, `ChatMessage`, `ChatInput` e `TypingIndicator` do diretório apropriado.
2. Defina os estados iniciais da sua aplicação React, como um array vazio para `messages` e um valor booleano `false` para `isLoading`.
3. Crie uma função assíncrona `handleSend` que receberá o conteúdo da mensagem.
4. Dentro dessa função, atualize o array de mensagens incluindo o conteúdo recebido com a role `user`.
5. Logo após, ative o estado `isLoading` (passando para `true`) e inicie a chamada para sua API ou LLM. Ao final do processamento, retorne `isLoading` para `false`.
6. No retorno do componente (JSX), encapsule tudo em um `<ChatContainer>`.
7. Itere sobre o array de mensagens mapeando cada item para um componente `<ChatMessage>` com a devida propriedade `role` e `content`.
8. Renderize o `<TypingIndicator />` condicionalmente quando `isLoading` for verdadeiro.
9. Finalize adicionando o componente `<ChatInput>` recebendo a função `handleSend` no evento `onSubmit` e repassando o `isLoading` para o atributo `disabled`.
