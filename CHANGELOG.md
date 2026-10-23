# Histórico de mudanças

## 0.1.17 alpha — Estrutura visual do aplicativo

- Barra superior com áreas separadas para marca, contexto, seleção de personagem e controles da janela.
- Menu lateral com grupos, indicador azul da página selecionada e adaptação à largura da janela.
- Fundos neutros em cinza chumbo, bordas discretas e conteúdo centralizado em monitores largos.
- Seleção de personagens, configurações, módulos e atualização automática preservados. Banner e rotina serão reformulados em uma próxima etapa.
- 167 testes aprovados; navegação, isolamento dos personagens, rolagem e renderização em diferentes tamanhos conferidos.

## 0.1.16 alpha — Tela Módulos

- Novo item Módulos com cartões de Medidor de dano e Rotina do personagem, sem funções ainda não implementadas.
- Chaves globais com salvamento automático em modules.json. Desligar não apaga dados ou configurações.
- Medidor desligado interrompe contagem, suspende novas consultas de CP e oculta o overlay. Reativar começa uma nova medição usando a identificação disponível.
- Rotina desligada não recebe novas observações de atividades e oculta os cartões, os recursos e os saldos do banner. Identificação básica e perfil continuam disponíveis.
- Ações Abrir e Configurações conectadas às telas existentes. Menu e botões respeitam módulos desligados.
- Regra de integrar futuras funções independentes à tela Módulos documentada em AGENTS.md e incluída no pacote fonte.

## 0.1.15 alpha — Tema cinza chumbo e azul

- Fundos cinza chumbo e superfícies neutras em Início, menu lateral, barra superior, configurações, cartões e overlay.
- Azul nas seleções, controles, botões, foco e indicadores; cores de classe preservadas nos dados do personagem e nas barras.
- Tipografia sem serifa consistente nos títulos, bordas mais discretas e degradês suaves nos painéis.
- Navegação, controles, escala, leitura de combate e preferências mantidos.

## 0.1.14 alpha — Ícones de classe no overlay — validação local

- Emblemas das classes substituem as iniciais nas linhas de DPS, cura e grupo.
- Imagens incluídas no aplicativo e carregadas uma única vez, sem requisições durante o combate.
- Nome da classe disponível no tooltip e para acessibilidade; classe ainda desconhecida usa uma silhueta neutra.

## 0.1.13 alpha — Overlay de DPS/cura e Combat Power

- Combat Power conectado à consulta oficial por nome e servidor, sem baixar retratos e sem interromper a captura de DPS/cura.
- Consultas sequenciais, cache de cinco minutos, novas tentativas após falhas e expiração de leituras antigas. Somente identidades confirmadas do personagem local e do grupo são consultadas.
- Tooltip informa a origem e o possível atraso do CP em relação ao jogo. Gear Score e prazo de berserk continuam sem leitor validado.
- Consulta real do Skkar retornou 116.528, compatível com 116,5 mil informado no jogo.
- DPS, cura e exibição do CP confirmados pelo usuário na instalação local. 162 testes automatizados aprovados. Leitura de aliados ainda aguarda validação ao vivo em party.

## 0.1.12 alpha — Overlay de dano e cura — validação local

- Overlay independente com modos de DPS e cura, ranking, totais, participação e duração.
- Eventos diretos e periódicos lidos na mesma captura passiva da identificação e das atividades.
- Contagem por identidade/servidor, grupo confirmado e dono explícito de invocações, com limites de memória e recuperação após perda de dados.
- Preferências de combate e exibição aplicadas ao vivo.
- Mover, redimensionar, travar para passar cliques, editar, mostrar/ocultar e reposicionar; posição e tamanho salvos localmente.
- GS/CP permanecem indisponíveis até leitura validada. Berserk só é mostrado com prazo explícito confirmado; ainda não há leitor desse prazo nesta versão.

## 0.1.11 alpha — Configurações de combate e exibição

- Seção Exibição habilitada, com 16 preferências para barras e janelas de dano/cura.
- Seleção eDPS/aDPS, Combat Power/Gear Score, formato do resumo, visibilidade, identificação dos jogadores e controles rápidos.
- Ajustes de opacidade, escala, intervalo de atualização e atraso para ocultar, com validação e salvamento automático.
- Arquivos de preferências anteriores mantêm os valores de Combate e recebem os padrões de Exibição.
- Esta etapa prepara as preferências; o motor de DPS/cura ainda não está conectado.

## 0.1.10 alpha — Configurações de combate — validação local

- Novo item Medidor de dano com as seções Combate, Exibição e Atalhos; as duas últimas aguardam implementação.
- Configuração de inatividade, pausa de chefe, modo farm, pausa entre packs, filtro de alvos, escopo do grupo e duração no boneco de treino.
- Preferências globais salvas localmente, com validação, gravação atômica e preservação dos dados dos personagens.
- Esta etapa configura o futuro overlay de DPS e cura; ainda não inicia medição em tempo real.

## 0.1.9 alpha — Seletor global e interface atualizada

- Seletor de personagens na barra superior, sem a opção de todos os personagens.
- Banner, retrato, classe, carteira, recursos e rotina acompanham a seleção, com proteção contra respostas atrasadas e cache limitado de perfis.
- Barra de rolagem fina com cantos arredondados e destaque ao arrastar.

## 0.1.8 alpha — Suavização das fontes — validação local

- Renderização de texto padronizada em ClearType, métricas naturais e hinting estático.
- Superfície principal opaca, com alinhamento de elementos à grade de pixels.
- Recorte e máscara ficam restritos ao retrato, fora da camada de texto do banner.
- Pequeno aumento dos menores rótulos e das descrições dos cartões para melhorar a leitura.
- Preservados o layout, os cartões em grade e os dados do personagem.
## 0.1.7 alpha — Cartões expandidos — validação local

- Cartões de atividades concluídas ou sem entradas ficam lado a lado conforme a largura disponível.
- Removidos o fundo e a borda externos dos grupos de cartões expandidos, incluindo leituras pendentes.
- Mantidos os cartões individuais e o comportamento de expandir/recolher. Conferência em uma, duas e três colunas.
## 0.1.6 alpha — Mescla visual — validação local

- Banner com retrato grande, saudação serifada, degradê contínuo e detalhes na cor da classe.
- Carteira permanece no banner, em região separada da imagem.
- Cartões de atividades retornam com valores em destaque e cores de periodicidade; a quantidade de colunas acompanha a largura disponível.
- Mantidos o painel separado de recursos, os detalhes expansíveis, o filtro da rotina e os controles de atualização no rodapé.
- Menu lateral intermediário entre as duas propostas, com botão Início identificado.
- Conferência visual em quatro larguras e cenários de dados ausentes, nomes longos e valores grandes; 105 testes aprovados.
## 0.1.5 alpha — Reformulação UX/UI — validação local

- Nova composição com navegação compacta, perfil separado e rotina como área principal.
- Retrato em área exclusiva, sem informações sobrepostas. Nome e borda do retrato preservam a cor da classe.
- Kinah e Pontos do Abismo junto ao perfil; energia e entradas em painel de recursos com identidade e última leitura visíveis.
- Atividades em lista alinhada, com valores, personagem, periodicidade e prazo de reset.
- Leituras pendentes e atividades concluídas ficam em grupos expansíveis, com foco de teclado visível.
- Controles de atualização passam para a barra inferior da aplicação.
- Tokens compartilhados de cores, superfícies e tipografia; carteira se reorganiza em janelas estreitas.
- 105 testes aprovados. Renderizações em janela mínima, padrão e ampla; cenários sintéticos de nome longo, valores grandes, falta de retrato e expansão de detalhes.
- Pesquisa e referências registradas na skill pessoal ux-ui-design e nas decisões de design locais. A pesquisa orienta a proposta; não representa estudo com usuários do Daeva Nexus.
## 0.1.4 alpha — Recursos no banner — 22/10/2026

- Tipografia compacta em Segoe UI e saudação em Palatino Linotype, com hierarquia baseada na referência visual.
- Banner principal reúne Energia Odyle, tempo no Abismo, Pesadelo, chaves do Shugo, Kinah, Pontos do Abismo, Rito de Ascensão, masmorra diária e chaves da Invasão.
- Energia e entradas extras permanecem separadas dos valores normais. Capacidade premium depende da assinatura informada pelo jogo.
- Moedas são lidas dos registros de inventário do personagem identificado. Kinah total, vinculado e livre são distinguidos; ausência de leitura não é interpretada como saldo zero.
- Troca de personagem limpa a apresentação anterior; o histórico segue isolado por nome e servidor.
- Leitura de moedas validada com testes de protocolo; conferência ao vivo dos saldos ainda pendente. Os campos aguardam dados até receber registros válidos.
- Interface conferida nas larguras de 850, 1020 e 1400 pixels, nos dois perfis conhecidos e sem personagem conectado.
- As sete atividades adiadas continuam ocultas.
- 104 testes automatizados aprovados, incluindo saldos absolutos, associação ao personagem, limites de moeda e atualização do banner.
## 0.1.3 alpha — Rotina por personagem — 22/10/2026

- Seção Sua rotina abaixo do banner, com seleção do personagem atual, outro personagem ou todos.
- Cartões de atividades diárias e semanais, alertas de recursos cheios e contagem até o reset.
- Entradas normais e extras de Pesadelo exibidas separadamente; extras continuam disponíveis quando as normais acabam.
- Shugo usa o contador conferido no jogo: chaves normais e extras separadas. Um contador homônimo sem finalidade confirmada fica oculto e não gera alertas.
- Leitura automática dos contadores recebidos do jogo, incluindo mensagens compactadas, com associação à identidade confirmada.
- Missões aceitas separadas das concluídas; mensagem de login incompatível é descartada.
- Compra de Energia de Od na Associação Brisa validada ao vivo em 20/20, com o reset informado pelo servidor. Leituras de loja são preservadas durante a troca de personagem até vencerem ou serem atualizadas.
- Compra da Pedra da Fenda do Piso Inferior do Abismo (7D) identificada e validada em 2/7. O limite é por personagem, não compartilhado por servidor. Uma lista atualiza todos os produtos reconhecidos sem descartar um deles.
- Captura permanece aberta durante mudanças de conexão do jogo, com confirmação de propriedade pelo Windows antes do envio de dados ao leitor.
- Histórico local dos contadores por personagem e servidor, sem gravar pacotes brutos.
- As sete atividades ainda sem leitura implementada ficam ocultas, preservadas para uma etapa futura. Atividades implementadas que aguardam registro continuam indicando dados indisponíveis. Seção de recursos e contadores adicionais removida da interface.
- Valores de Pesadelo, Rito e Abismo conferidos com o jogador; deveres validados ao vivo de 0 para 1 concluída.
- 99 testes aprovados, incluindo remontagem TCP, isolamento entre personagens, troca de conexão, reset, bilhetes extras, contador correto de Shugo, preservação das compras, múltiplos produtos na lista e atualização do diário.

## 0.1.2 alpha — Retratos e cores por classe — 22/10/2026

- O banner usa a cor da classe no nome, identificação, bordas e tonalidade do fundo.
- Chanter mantém o laranja; Espiritualista usa magenta. Classes desconhecidas usam um tom neutro.
- Retrato prioriza a URL do perfil detalhado e faz uma nova tentativa curta em falhas temporárias.
- Consultas sem retrato recebem novas tentativas automáticas em 15, 30 e 60 segundos, depois retornam ao intervalo normal.
- Atualizações do mesmo personagem preservam o retrato já carregado. Trocas de personagem descartam a imagem e o tema anteriores.
- Falhas de exibição de imagem não são ocultadas pelo sucesso da consulta textual.
- 64 testes aprovados e renderização dos dois perfis reais conferida.

## 0.1.1 alpha — Instalação e atualização — 22/10/2026

- Instalador Windows em português com escolha da pasta, atalhos e desinstalação.
- Verificação automática ao abrir e a cada seis horas, com verificação manual disponível.
- Aviso de nova versão, botão para baixar/instalar e opção de cancelar o download.
- Atualização na pasta atual, preservação do perfil e reabertura do aplicativo.
- Manifesto RSA-PSS, conferência SHA-256 e rejeição de versões do antigo medidor.

## 0.1.0 — Reconstrução do projeto — 22/10/2026

O projeto foi refeito do zero, com nova organização e identidade **Daeva Nexus**.

- Nova base separada entre apresentação, aplicação e integração de dados.
- Tela Início com menu lateral e cartão de nome, classe, nível e retrato do personagem.
- Consulta ao perfil público da NCSoft para a América do Sul.
- Cabeçalho com indicadores compactos, saudação por horário e nome em destaque.
- Transição suave do retrato sobre o fundo do cartão.
- Janela personalizada com controles de minimizar, maximizar/restaurar e fechar.
- 29 testes automatizados aprovados na validação inicial.

Versão de desenvolvimento. A identificação automática em uma nova sessão do jogo ainda precisa de validação ponta a ponta.
