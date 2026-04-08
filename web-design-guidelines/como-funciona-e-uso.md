# Como Funciona e Uso

A skill **Web Design Guidelines** executa uma revisão automatizada de arquivos em busca de conformidade com as "Web Interface Guidelines" oficiais da Vercel. 

## Como a Ferramenta Funciona Internamente

O fluxo de auditoria segue estes passos estritos:
1. **Busca Remota (Fetch):** A skill faz o fetch das diretrizes mais recentes a partir de um repositório central antes de cada revisão, garantindo que as regras não fiquem desatualizadas. 
   1. A fonte é acessada via: `https://raw.githubusercontent.com/vercel-labs/web-interface-guidelines/main/command.md`
2. **Leitura:** Lê os arquivos especificados por meio de um padrão (pattern) ou caminho. Se não forem fornecidos, o usuário será solicitado a informar quais arquivos devem ser avaliados.
3. **Validação:** Checa o conteúdo contra as mais de 100 regras listadas no conteúdo baixado remotamente.
4. **Relatório:** Emite as descobertas em formato sucinto, seguindo a estrutura `arquivo:linha` (file:line), o que facilita muito encontrar e consertar o código imediatamente.

## Quando Acionar a Skill

Use esta skill durante sessões de pareamento com IA usando comandos naturais, como:
1. *"Review my UI"* (Revise minha UI)
2. *"Check accessibility"* (Verifique a acessibilidade)
3. *"Audit design"* (Audite o design)
4. *"Review UX"* (Revise a UX)
5. *"Check my site against best practices"* (Verifique meu site contra as melhores práticas)

Assim que o comando for processado, a skill rodará a auditoria e retornará os pontos de correção no terminal/interface de chat.