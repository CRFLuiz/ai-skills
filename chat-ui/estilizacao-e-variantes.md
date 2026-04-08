# Estilização e Variantes de Mensagem

1. O componente `ChatMessage` possui variantes baseadas no papel (role) da entidade que enviou a mensagem, adaptando seu alinhamento na tela automaticamente.
2. A role `user` é usada para as mensagens do usuário humano e aparece alinhada à direita da tela.
3. A role `assistant` representa as respostas da inteligência artificial e aparece alinhada à esquerda.
4. A role `system` destina-se às mensagens de sistema e aparece centralizada no layout.
5. Em relação à estilização, todos os componentes fazem uso de Tailwind CSS e dos tokens de design nativos do `shadcn/ui`. É possível passar propriedades adicionais de classe (ex: `className="bg-muted"`) para customizar a aparência padrão.
