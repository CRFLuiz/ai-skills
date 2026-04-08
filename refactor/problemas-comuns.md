# Problemas Comuns e Soluções

## Problemas de Código (Code Smells)

1. **Método ou Função Longa:** Funções que fazem muitas coisas devem ser divididas em funções menores e focadas.
2. **Código Duplicado:** Lógica repetida em vários lugares deve ser extraída para funções ou variáveis comuns.
3. **Classe ou Módulo Grande:** Objetos "Deus" que sabem demais devem ser divididos em classes com uma única responsabilidade.
4. **Lista Longa de Parâmetros:** Muitos parâmetros devem ser agrupados em objetos de dados ou interfaces relacionadas. O padrão Builder também pode ser útil.
5. **Inveja de Funcionalidade (Feature Envy):** Um método que usa mais os dados de outro objeto do que os seus próprios. A lógica deve ser movida para o objeto que possui os dados.
6. **Obsessão por Primitivos:** Usar tipos primitivos para conceitos de domínio. Em vez disso, crie tipos de domínio específicos (como classes para Email ou Telefone).
