# Funcionalidades Avançadas (Autoscaling, Branching e Scale-to-Zero)

1. **Branching**: A ramificação no Neon é instantânea e funciona através de um clone "copy-on-write" (sem cópia completa de dados).
2. Cada "branch" possui seu próprio endpoint computacional, sendo ideal para criar ambientes isolados, testar migrações de esquema, fazer deploys de preview e automatizar o ciclo de vida dos ramos.
3. Utilize a CLI `neonctl` ou o servidor MCP para criar, inspecionar e comparar as "branches".
4. **Autoscaling**: O Neon dimensiona automaticamente o poder computacional para lidar com a carga de trabalho. Para entender a alocação de "CU" (Compute Units), consulte a documentação oficial.
5. **Scale to Zero**: Recursos computacionais inativos são suspensos automaticamente (o padrão é 5 minutos, mas é configurável) para otimizar os custos com ociosidade.
6. A primeira consulta após uma suspensão gera uma penalidade de "cold-start" (que pode durar centenas de milissegundos), mas o armazenamento permanece ativo independentemente da computação.
