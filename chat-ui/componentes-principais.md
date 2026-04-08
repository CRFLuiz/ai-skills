# Componentes Principais

1. **ChatContainer** (`@/registry/blocks/chat/chat-container`): O elemento raiz que deve envolver e gerenciar a lista de mensagens.
2. **ChatMessage** (`@/registry/blocks/chat/chat-message`): O componente responsável por exibir as mensagens individuais na tela. Ele recebe as propriedades de `role` e `content`.
3. **ChatInput** (`@/registry/blocks/chat/chat-input`): O campo de digitação onde o usuário insere a mensagem. Permite configurar eventos como `onSubmit`, além de propriedades como `placeholder` e estado `disabled`.
4. **TypingIndicator** (`@/registry/blocks/chat/typing-indicator`): O indicador visual que deve ser ativado (renderizado condicionalmente) enquanto a resposta da inteligência artificial estiver sendo aguardada.
