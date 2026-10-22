# Histórico de mudanças

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
