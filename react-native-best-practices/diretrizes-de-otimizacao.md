# Diretrizes de Otimização Prioritárias

1. **FPS e Re-renderizações (Impacto: Crítico)**
   1. Perfil primeiro: Abra o React Native DevTools pressionando 'j' no Metro ou agitando o dispositivo.
   2. Substitua `ScrollView` por `FlatList` ou `FlashList` para listas.
   3. Use o React Compiler para memorização automática.
   4. Utilize estado atômico (Jotai/Zustand) para reduzir re-renderizações.
   5. Use `useDeferredValue` para cálculos custosos.

2. **Tamanho do Pacote (Bundle Size) (Impacto: Crítico)**
   1. Analise o bundle usando o comando `react-native bundle` com as opções `--dev false --minify true` e verifique com `source-map-explorer`.
   2. Evite importações do tipo "barrel" (importe diretamente da fonte).
   3. Remova polyfills do Intl desnecessários apenas após verificar a API do Hermes.
   4. Habilite a eliminação de código morto (tree shaking) (Expo SDK 52+ ou Re.Pack).
   5. Habilite o R8 para redução de código nativo no Android.

3. **Otimização do Tempo de Inicialização (TTI) (Impacto: Alto)**
   1. Meça o TTI usando `react-native-performance` para obter os marcadores.
   2. Meça apenas as inicializações frias (cold starts).
   3. Desative a compactação do bundle JS no Android (habilita o mmap do Hermes).
   4. Use navegação nativa (`react-native-screens`).
   5. Pré-carregue telas pesadas usadas com frequência antes de navegar para elas.

4. **Desempenho Nativo (Impacto: Alto)**
   1. Crie perfil nativo: Use o Xcode Instruments (Time Profiler) no iOS e o CPU Profiler no Android Studio.
   2. Use threads em segundo plano para trabalhos nativos pesados.
   3. Prefira métodos assíncronos nos Turbo Modules em vez de síncronos.
   4. Use C++ para código crítico em desempenho em plataformas cruzadas.

5. **Mapeamento de Problemas**
   1. Se o aplicativo parecer lento ou travado: Comece medindo o FPS e criando um perfil React.
   2. Se houver muitas re-renderizações: Comece com o perfil React e avalie o React Compiler.
   3. Se a inicialização for lenta: Meça o TTI e analise o bundle JS.
   4. Se o tamanho do aplicativo for grande: Analise o tamanho do aplicativo e utilize o R8 no Android.
   5. Se a memória estiver crescendo: Investigue vazamentos de memória JS ou nativos.
   6. Se houver queda de quadros em animações: Revise as animações com Reanimated.
