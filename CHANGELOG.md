# Histórico de mudanças

## 0.1.24 alpha — Chefes de campo (F08)

- Tela com regiões, servidor observado, estados e retornos informados pelo jogo. Leitura direta da lista de monstros de campo, sem cadastro manual ou agenda de respawn presumida.
- Avisos por chefe com antecedência, Windows, janela sobreposta, som opcional e teste. Novo módulo independente, preservando preferências e observações ao desligar.
- Listas fora de ordem resolvidas pelo número do chefe; entradas incompletas, duplicadas, conexões antigas e regiões sem vínculo confirmado são rejeitadas. Leituras vencidas são históricas; timer encerrado aguarda nova consulta.
- 256 testes aprovados, verificações WPF e comparação ao vivo do Gartua Imortal em Altgard: cerca de 2h56 para o retorno, compatível com o jogo. Outras regiões ainda não conferidas ao vivo. Canal não identificado; consulta recente exigida para avisos.
- Fontes, comparação ao vivo e limites em docs/field-bosses-research.json e docs/field-bosses-validation.json.

## 0.1.23 alpha — Eventos e notificações (F07)

- Tela Eventos com agenda prevista da América do Sul: Festival Shugo, Invasão Dimensional, Fenda do Espaço-Tempo e resets diário/semanal. Próximos horários em Brasília e contagem automática, sem cadastro manual.
- Seleção por evento, antecedência, aviso Windows, janela sobreposta, som opcional e botão de teste. Preferências e prevenção de avisos repetidos persistidas com escrita atômica e recuperação explícita em caso de corrupção.
- Eventos integrado a Módulos: desligar interrompe o timer e oculta avisos, preservando preferências. Rotina e medidor continuam independentes.
- 234 testes aprovados e verificações WPF de Eventos, Módulos e Análise sem erros de binding. Envio nativo aceito pelo Windows; apresentação depende das configurações do sistema. Uma contagem aproximada da Fenda foi comparada com o jogo; demais horários permanecem previstos.
- Fontes e limites documentados em docs/events-research.json e docs/events-validation.json. Horários previstos, sem presumir ocorrência ao vivo.

## 0.1.22 alpha — Rotina sempre ativa e navegação do medidor

- Rotina, recursos e saldos do personagem ficam sempre ativos e saem da tela Módulos. A preferência antiga Routine é ignorada, preservando as atividades e a escolha do Medidor de dano.
- 216 testes aprovados, incluindo compatibilidade dos arquivos antigos com rotina desativada e persistência da preferência do medidor. Conferida a atualização da rotina e dos saldos com o medidor desligado.
- Análise, Combate, Exibição e a indicação de Atalhos em breve passam para abas horizontais dentro da área do Medidor de dano.
- Barra lateral mantém apenas os acessos principais; seleção da seção, entrada por Módulos e abertura da análise pelo overlay preservadas.
- Navegação, controles e salvamento conferidos nas verificações WPF de Análise, Combate e Exibição, com renders em janela mínima, padrão, larga e raster de 150%.

## 0.1.21 alpha — Análise de combate (F02)

- Tela Análise dentro do Medidor de dano: participante selecionado, resumo do encontro e alternância entre dano e cura. A seleção inicial usa o personagem capturado, separada do seletor do Início.
- Detalhes por ID exato da habilidade: valor, participação, DPS/HPS, eventos observados e menor/média/maior evento. Variantes não são fundidas por semelhança de nome. Eventos não são apresentados como usos, acertos únicos, críticos ou overheal.
- Catálogo local com nomes em português quando disponíveis e 359 ícones; identificação neutra para campos desconhecidos. Nenhum download é feito durante o combate.
- Removidos os botões Mostrar/Ocultar overlay, Editar overlay e Reposicionar da barra lateral, junto com o bloco auxiliar. A abertura continua em Módulos e na Análise.
- Clique em uma linha do overlay destravado abre a análise daquele personagem. Bloqueio, passagem de cliques e privacidade preservados.
- Agregação limitada a 512 IDs por participante, com excedentes agrupados e aviso parcial, sem perder os valores já aceitos. Resultado atual/final em memória; histórico persistente pertence à F03.
- 215 testes aprovados, incluindo a remontagem de mensagens até o detalhamento, reconciliação de valores, concorrência, invocações, homônimos e ciclo do módulo. Validações WPF de análise, Módulos e overlay aprovadas, sem erros de binding. Conferência ao vivo da party ainda pendente. 

## 0.1.20 alpha — Confiabilidade da leitura de combate

- Leitura estrutural e limitada das mensagens de party/aliança, incluindo lista completa, entrada, reconexão, troca de líder, saída e dissolução. Lista do recrutador não concede participação no grupo.
- Identidade vinculada ao servidor de origem; integrantes sem ID disponível continuam listados sem autorizar dano de personagens próximos.
- Mudança de mapa invalida IDs temporários e preserva o resultado encerrado. Mensagens incompletas não provocam um reset presumido.
- Uma conexão identificada alimenta o combate; dados e falhas de conexões anteriores não encerram a sessão nova. Listas de grupo anteriores à identificação são mantidas apenas em forma decodificada, com limites e validade.
- Saída do grupo interrompe novos créditos sem remover o dano já aceito. Atualizações de grupo antigas e IDs reutilizados não transferem resultados entre personagens.
- Contrato de contribuições aceitas preparado para habilidades e histórico, com origem direta/periódica e dono da invocação resolvido, sem gerar estatísticas ainda não lidas.
- 205 testes aprovados e verificações WPF de Módulos e overlay. Diagnóstico solo recebeu 47 contribuições de dano (490.956), identificação e transição de mapa, sem erro de leitura no intervalo observado. Validação ao vivo da party/aliança permanece pendente.

## 0.1.19 alpha — Módulos, configurações e overlay

### Overlay

- Overlay com fundo cinza chumbo, controles neutros, destaques azuis e barras finas nas cores de classe.
- Nome e CP/GS na mesma linha, ícone e classe próximos à identificação, valores de DPS/HPS e totais alinhados.
- Disposição compacta em larguras menores, preservando identificação e rolagem; modos DPS, Cura e Grupo mantidos.
- Preferências de escala, opacidade, foco, privacidade e colunas preservadas; aviso explícito para leitura parcial.
- Brushes congelados reutilizados nas atualizações; sem mudanças no protocolo ou cálculo de combate.
- 169 testes aprovados, verificações WPF de ações, modos e escalas, e nova conferência do desligamento pelo módulo.

### Módulos e configurações

- Módulos com estados explícitos, ícones, ações Abrir e Configurações diferenciadas e apresentação compatível com a nova tela inicial.
- Combate e Exibição organizados em grupos com superfícies neutras, detalhes azuis e controles padronizados.
- Componente compartilhado de configuração adapta campos, seletores e sliders a janelas estreitas sem reduzir os textos.
- Preferências, validação dos campos, salvamento automático e ciclo de ativação dos módulos preservados.
- 169 testes aprovados; verificações WPF de navegação, sete opções de Combate, dezesseis de Exibição, ativação/desativação, redimensionamento e raster de 150%.

## 0.1.18 alpha — Nova tela inicial

- Banner com identificação, ícone de classe, retrato e carteira em regiões separadas, adaptando a disposição à largura da janela.
- Faixa de Energia Odyle, tempo no Abismo e chaves do Shugo. Demais recursos preservados em uma seção expansível, com personagem e última leitura próximos aos valores.
- Rotina em linhas alinhadas e filtros Tudo, Diário e Semanal. O filtro não altera os saldos, a captura ou a identidade selecionada.
- Estados de leitura pendente, zero, bônus, conclusão e ausência de entradas preservados.
- 169 testes aprovados e verificações visuais de tamanhos, nomes longos, saldos grandes, retrato ausente, expansão e raster de 150%.

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
