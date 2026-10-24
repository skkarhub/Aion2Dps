# Daeva Nexus

O projeto foi refeito do zero e passa a se chamar **Daeva Nexus**. A versão atual é **0.1.25 alpha**, com Dano final e Histórico, Chefes de campo, Eventos e notificações, rotina sempre ativa e abas de Análise, Dano final, Histórico, Combate e Exibição dentro do Medidor de dano. Mantém Módulos, configurações e overlay em cinza chumbo e azul. Inclui tela inicial com recursos compactos e rotina em linhas, ícones de classe e Combat Power no overlay.

O menu **Início** reúne o cartão do personagem (nome, classe, nível e retrato) e a seção **Sua rotina**, com atividades diárias, semanais e recursos separados por personagem.

O seletor da barra superior permite consultar individualmente cada personagem já identificado. **Não perca** destaca recursos cheios; **Falta fazer** mostra atividades com leitura disponível; **Dados indisponíveis** mantém visível o que ainda não pôde ser lido. Os dados ficam salvos neste PC, por nome e servidor, em `%LOCALAPPDATA%/DaevaNexus/activities.json`. Personagens desconectados mostram a última leitura, e valores vencidos após o reset aguardam nova confirmação do jogo.

Foram conferidos ao vivo Shugo (9 normais e 5 extras), Pesadelo (entradas normais e extras separadas), Rito de Ascensão, tempo no Abismo, a passagem de zero para uma Missão de Dever concluída e a compra de Energia de Od na Associação Brisa (20/20, com reset enviado pelo servidor). No teste, o contador da loja chegou após reabrir completamente o jogo; a seleção de personagens e a troca de abas não o reenviaram. Leituras de loja confirmadas são preservadas ao receber uma nova lista de entradas, até seu prazo de validade ou atualização explícita. A compra de Pedras da Fenda do Piso Inferior do Abismo (7D), na Associação Brisa, também foi validada ao vivo em 2/7, por personagem; essa oferta é temporária e tem reset informado pelo servidor. Os sete cartões de Kinah, presença, corredores, suprimentos e crafts ficam ocultos enquanto a leitura automática não é implementada; as definições foram preservadas para uma etapa futura. Não há preenchimento manual nem conclusão presumida. Os horários desta versão para América do Sul usam 04h de Brasília diariamente e quarta-feira para o reset semanal.

O banner principal também reúne Energia Odyle, tempo no Abismo, entradas de Pesadelo, chaves do Shugo, Kinah, Pontos do Abismo, Rito de Ascensão, masmorra diária e chaves da Invasão. Bônus aparecem separados do saldo normal. Kinah total, vinculado e livre são distinguidos; um saldo parcial é identificado como tal. As moedas dependem do envio de inventário pelo jogo e ainda aguardam conferência ao vivo nesta versão. Campos sem registro válido exibem “—”, sem assumir zero. A data da última leitura e os detalhes individuais ficam disponíveis no banner.

O banner adapta nome, identificação, bordas e fundo à classe do personagem. Quando o serviço demora a entregar o retrato, há novas tentativas automáticas em 15, 30 e 60 segundos; depois o intervalo retorna a cinco minutos. A disponibilidade depende do serviço público. Uma atualização temporariamente sem imagem preserva o retrato do mesmo personagem, enquanto a troca de personagem limpa a imagem anterior.

## Leitura de combate — 0.1.20 alpha

A lista do recrutador não autoriza personagens como integrantes da party. Mensagens completas de party/aliança identificam os membros pelo servidor de origem; entradas, reconexões, liderança, saída e dissolução são tratadas separadamente. Um integrante sem ID disponível continua listado, sem atribuir dano de jogadores próximos. Ao sair do grupo, deixa de receber novos créditos, mas seu dano já aceito permanece no resultado da luta.

Mudanças de mapa invalidam os IDs temporários e preservam o resultado encerrado. Pacotes incompletos não provocam um reset presumido. Dados e falhas de conexões anteriores não encerram o combate da conexão atual identificada. Falhas de captura exigem nova identificação e confirmação do grupo.

205 testes automatizados aprovados, além de verificações WPF de Módulos e overlay. No diagnóstico solo foram recebidos 47 eventos de dano, somando 490.956, com identificação e transição de mapa, sem erro de leitura no intervalo observado. A comparação ao vivo dos aliados e de alianças continua pendente. A versão 0.1.20 preparou os eventos usados pela Análise da 0.1.21; histórico persistente continua previsto para a etapa F03.

## Interface — 0.1.21 alpha

A tela inicial usa Segoe UI e superfícies cinza neutras. O banner reúne nome, ícone e cor da classe, nível, servidor, retrato e carteira, com adaptação à largura da janela. Energia Odyle, tempo no Abismo e chaves do Shugo ficam em uma faixa de consulta rápida. Os demais recursos continuam disponíveis em Outros recursos. A rotina aparece em linhas alinhadas, com filtros Tudo, Diário e Semanal que afetam apenas essa lista. Leituras pendentes e atividades concluídas podem ser expandidas. A atualização continua na barra inferior. O seletor superior atualiza individualmente todos os dados apresentados do personagem; consultar outro perfil não altera a identidade usada para capturar dados do jogo. Saldos normais e bônus permanecem separados, e dados ausentes não são tratados como zero.

Módulos apresenta o Medidor de dano como função opcional, com estado explícito e ações Abrir/Configurações. Rotina, recursos e saldos do personagem permanecem sempre ativos, mesmo com o medidor desativado. A preferência antiga que desligava a rotina é ignorada sem apagar os dados anteriores. Combate e Exibição organizam as opções em grupos; os editores passam para baixo das descrições em janelas estreitas. O overlay mantém nome e CP/GS na mesma linha, ícone e classe próximos, valores alinhados e barras finas nas cores de classe. Em larguras menores, os valores passam para uma segunda linha. Escala, opacidade, foco, privacidade e leitura parcial permanecem disponíveis. Os 205 testes passaram, junto das verificações WPF de controles, modos, módulos e redimensionamento; não houve nova validação ao vivo em party nesta alteração. Esta versão reúne as melhorias de interface desenvolvidas após a 0.1.4. O código-fonte completo, com testes e instruções de compilação, está no arquivo `DaevaNexus-Source-0.1.22.zip` na [release 0.1.22](https://github.com/skkarhub/Aion2Dps/releases/tag/v0.1.22-alpha.1).
## Chefes de campo (F08)

O aplicativo lê a lista de monstros de campo consultada no mapa do jogo e mostra estado, retorno informado e última consulta, separados por região e servidor. Inclui seleção de chefes, antecedência, avisos Windows/janela, som opcional e teste, controlados pelo novo módulo Chefes de campo. O Gartua Imortal, em Altgard, foi comparado ao vivo com o jogo; 256 testes e verificações WPF passaram. Instalador e projeto completo na [release 0.1.24](https://github.com/skkarhub/Aion2Dps/releases/tag/v0.1.24-alpha.1).

O canal não foi identificado. Consulte novamente a lista após trocar de canal, mapa ou servidor. Após cinco minutos sem atualização, os dados viram histórico e deixam de gerar alertas; para retornos distantes, mantenha a lista aberta ou consulte-a novamente perto do prazo. O fim do timer não confirma que o chefe nasceu. Observações, preferências e claims ficam em `%LOCALAPPDATA%/DaevaNexus/field-bosses.json`. Não há cadastro manual nem compartilhamento de timers. Fontes e limites estão em `docs/field-bosses-research.json` e `docs/field-bosses-validation.json`.

## Dano final e histórico (F03)

A versão 0.1.25 acrescenta Dano final e Histórico dentro do Medidor de dano. Os encontros encerrados preservam ranking de dano/cura, taxas calculadas no encerramento e habilidades de cada personagem. O histórico pode ser reaberto depois de reiniciar, filtrado por personagem e servidor de origem, período no calendário de Brasília e alvo. Consultar os resultados não altera o combate atual. O resumo copiável respeita a opção de ocultar nomes dos outros jogadores.

Os arquivos ficam apenas neste PC, em `%LOCALAPPDATA%/DaevaNexus/combat-history`, e incluem identidades e estatísticas normalizadas, sem pacotes, endereços de rede ou IDs transitórios. A privacidade visual não anonimiza os arquivos. São mantidos até 200 encontros, por até 90 dias, respeitando 128 MiB de arquivos válidos; os mais antigos são removidos ao salvar novos. Dados inválidos são preservados com aviso. Falha de disco mantém tentativas enquanto o app estiver aberto; término abrupto pode perder pendentes. Agrupamento por DG e gráficos pertencem à próxima etapa.

273 testes passaram, com verificações WPF do histórico, análise ao vivo e Módulos. O teste real solo confirmou o encerramento e a reabertura de dois combates com valores preservados; um deles foi marcado como parcial. Party ainda não validada. Instalador e código-fonte completo na [release 0.1.25](https://github.com/skkarhub/Aion2Dps/releases/tag/v0.1.25-alpha.1). Arquitetura e validação em `docs/combat-history-design.json` e `docs/combat-history-validation.json`.

## Executar

### Eventos e notificações (F07)

Esta versão acrescenta Eventos a Módulos, com agenda prevista da América do Sul, próximos horários em Brasília e contagem regressiva para Festival Shugo, Invasão Dimensional, Fenda do Espaço-Tempo e resets diário/semanal. Permite escolher eventos, antecedência, avisos Windows, janela sobreposta e som opcional, além de testar o aviso. Desativar Eventos interrompe seu timer e oculta avisos sem afetar rotina ou medidor. O aplicativo deve permanecer aberto ou minimizado.

Os horários são calculados a partir de um catálogo embarcado, sem cadastro manual e sem confirmação ao vivo de ocorrência. Manutenções podem alterar a agenda. Preferências e prevenção de repetição ficam em `%LOCALAPPDATA%/DaevaNexus/events.json`; um arquivo inválido pausa os avisos até recuperação explícita. 234 testes e verificações WPF aprovados. Fontes, comparação aproximada da Fenda e limites estão em `docs/events-research.json` e `docs/events-validation.json`. O instalador e o código-fonte completo desta versão estão na [release 0.1.23](https://github.com/skkarhub/Aion2Dps/releases/tag/v0.1.23-alpha.1).

### Versão publicada

Baixe `DaevaNexus-Setup-0.1.24.exe` na seção Releases. O assistente permite escolher a pasta e criar um atalho na área de trabalho. O aplicativo aparece na lista de aplicativos instalados do Windows. O instalador é por usuário e não instala o Npcap automaticamente.

O app verifica atualizações ao abrir e a cada seis horas. Quando há uma versão nova, mostra um aviso e o botão **Atualizar**. Ao clicar, baixa o instalador, confere a assinatura do manifesto e o SHA-256 do arquivo, instala na pasta atual e reabre o aplicativo. O download pode ser cancelado. O perfil salvo é preservado, inclusive na desinstalação. As versões do antigo Aion2Dps são ignoradas.

A primeira migração da versão portátil 0.1.0 exige executar o instalador; ela ainda não tinha o atualizador. O pacote não possui certificado comercial Authenticode; o Windows pode exibir a identificação de editor desconhecido. A assinatura RSA do canal de atualização é separada dessa identificação do Windows.

Abra `artifacts/app/DaevaNexus.exe`. A pasta precisa permanecer completa; o executável utiliza os arquivos que a acompanham. A compilação é autocontida para Windows x64, sem exigir instalação separada do .NET.

A identificação é automática e passiva, somente nas conexões IPv4 pertencentes ao AION2.exe, usando o Npcap já instalado. Inicie o aplicativo antes de entrar no personagem para receber a identificação. Caso ele seja iniciado com o personagem já conectado, pode ser necessário aguardar o próximo envio de identificação pelo jogo.

O último nome/servidor confirmado fica em `%LOCALAPPDATA%/DaevaNexus/character.json`, para recarregar o perfil na próxima abertura. Isso não representa confirmação de que o personagem está online. Não há formulário de cadastro manual.

O perfil e o retrato são consultados nos serviços públicos da NCSoft, na região América do Sul. Se não houver perfil público ou retrato disponível, o aplicativo exibe um estado de espera/indisponibilidade, sem inventar dados. Nome e servidor precisam coincidir exatamente; resultados parciais de busca são rejeitados.

## Estrutura

- `src/DaevaNexus.Core`: identidade, perfil, contratos e coordenação.
- `src/DaevaNexus.Infrastructure`: consulta pública, identificação passiva e persistência mínima.
- `src/DaevaNexus.Desktop`: WPF, apresentação e composição.
- `tests/DaevaNexus.Tests`: validação de identidade, remontagem TCP, respostas da API e troca de personagem.
- `src/DaevaNexus.Desktop/Assets`: arquivos de marca usados na interface.

Não há leitura da memória do jogo, automação de comandos, escrita no cliente, upload de captura ou pacotes brutos em disco. Os buffers de captura, conexão e resposta HTTP são limitados. Retratos são obtidos em profileimg.plaync.com; somente redirecionamentos explícitos para a rota de retratos em fizz-download.playnccdn.com são aceitos, com limite de dois saltos. Os redirecionamentos automáticos estão desabilitados.

## Desenvolvimento

Requer PowerShell 7 e o SDK indicado em `global.json`. Execute `./build.ps1` para testar e gerar a pasta executável. `./build.ps1 -Launch` também abre o aplicativo.

`./package.ps1` também gera o instalador usando Inno Setup 6.7.3 e o manifesto assinado. A chave privada de publicação fica protegida com DPAPI fora do repositório, em `%LOCALAPPDATA%/DaevaNexusPublisher/release-key.dpapi`. Ela não é necessária para compilar/testar o app nem para compilar um instalador de desenvolvimento. Não substitua a chave pública de versões já distribuídas: uma chave nova exige um processo explícito de migração. O manifesto é assinado com RSA-PSS/SHA-256; downloads usam HTTPS, limites de tamanho e tempo e uma lista explícita de hosts GitHub.

O parâmetro opcional `--profile NOME SERVIDOR` permite inicializar o vínculo de um perfil previamente confirmado em desenvolvimento; nenhum personagem específico está embutido no código.

O histórico desta reconstrução está em [CHANGELOG.md](CHANGELOG.md).

## Análise de combate — 0.1.21 alpha

A tela **Medidor de dano → Análise** acompanha o encontro atual ou o último resultado encerrado nesta sessão. Selecione o personagem capturado ou outro participante com identidade confirmada, e alterne entre **Dano** e **Cura**. O seletor do Início não altera a atribuição do combate.

Cada linha mostra nome/ícone da habilidade, ID, total, participação, taxa por segundo e eventos observados. A seleção de uma habilidade apresenta o menor, a média e o maior evento, além da origem direta/periódica quando disponível. A taxa usa a mesma duração escolhida nas configurações (eDPS/aDPS ou HPS). Eventos podem incluir vários alvos e efeitos periódicos: não são contagem de usos/acertos únicos, críticos ou overheal. Habilidades sem metadados mantêm seu ID e um ícone neutro. Algumas traduções ainda aparecem em inglês, identificadas no tooltip.

Clique em um personagem no overlay **destravado** para abrir sua análise. A chave **Medidor de dano** em Módulos controla contagem, overlay e análise juntos. A tela atualiza enquanto está aberta, sem gravar eventos brutos nem fazer consultas de nomes/imagens durante o combate. Há limite de 512 IDs por participante; excedentes aparecem agrupados com indicação de leitura parcial. Não há histórico persistente nesta etapa.

216 testes automatizados e verificações WPF de análise, Módulos e overlay aprovados. Os controles auxiliares de overlay foram removidos da barra lateral; a abertura segue disponível em Módulos e na Análise. A validação ao vivo em party continua pendente. Os testes estão incluídos no pacote de código-fonte da release.

## Configurações do medidor

O segundo item do menu, **Medidor de dano**, tem abas internas para **Análise**, **Combate** e **Exibição**. **Atalhos** aparece como próxima etapa. A barra lateral mantém somente os acessos principais. A tela permite configurar o tempo ocioso (20 s), manter lutas de chefe abertas (ligado), modo farm (ligado), pausa entre packs (10 s), modo de alvo (todos), apenas você e o grupo (ligado) e duração no boneco de treino (desligado). Os tempos editáveis aceitam inteiros entre 1 e 300 segundos. Os campos vazios ou inválidos são destacados e não substituem a última configuração salva.

As preferências são globais para o aplicativo e ficam em `%LOCALAPPDATA%/DaevaNexus/combat-settings.json`, separadas da identidade e dos contadores de cada personagem. As alterações válidas são salvas automaticamente após uma pequena pausa e ao fechar. As opções são aplicadas ao motor de combate e ao overlay conectado descritos abaixo.

## Exibição do medidor

**Medidor de dano → Exibição** configura as barras e a janela do overlay. Padrões: eDPS, Combat Power ao lado do nome, dano total visível, DPS do grupo ligado, ocultar fora de combate após 15 s, timer de berserk ligado e resumo em uma linha. Nas janelas: fundo a 86%, foco desligado, botões Party/Todos e Grupo/DPS ocultos, nome da classe visível, nomes dos jogadores visíveis, escala de 90% e atualização a cada 150 ms.

A opacidade permite 10–100%, escala 60–160%, atualização 50–500 ms e atraso para ocultar 1–300 s. eDPS considera a duração do encontro; aDPS considera o intervalo do primeiro ao último golpe de cada jogador. Exibir o botão Party/Todos não muda sozinho a opção de contar apenas você e o grupo. Os sliders aceitam teclado, as preferências são salvas automaticamente junto de Combate e os arquivos anteriores recebem padrões sem perder os valores existentes. Atalhos permanece para a próxima etapa.

## Overlay de DPS e cura

O overlay é uma janela independente, visível sobre o jogo mesmo com a janela principal minimizada. Alterne entre **DPS** e **Cura** no cabeçalho. Cada personagem mostra taxa, total e participação; invocações só são creditadas quando o jogo identifica o dono. A leitura usa o Npcap existente e as conexões pertencentes ao AION2.exe. Nenhum comando é enviado ao jogo e nenhum pacote bruto é gravado. A identificação para o combate vem da captura, não do personagem selecionado no Início.

Abra o overlay em **Módulos → Medidor de dano → Abrir** ou em **Medidor de dano → Análise → Mostrar overlay**. Os controles auxiliares foram removidos da barra lateral. Arraste o título para mover e o canto para redimensionar; **Travar** deixa os cliques passarem ao jogo. O X do overlay só o oculta; fechar o aplicativo principal encerra ambas as janelas. O travamento não é restaurado na abertura, para manter a recuperação acessível. Posição, tamanho e visibilidade ficam em `overlay-placement.json`, sem nomes ou dados de combate.

Combate aplica inatividade, pausas de chefe, farm, filtros de alvo/grupo e duração de treino. O resultado do treino permanece congelado no limite escolhido, até uma pausa real ou Zerar. Exibição aplica eDPS/aDPS, colunas, soma do grupo, ocultação, foco, resumo, controles rápidos, privacidade, opacidade, escala e intervalo. A ocultação automática volta no próximo evento aceito; Mostrar overlay revela por dez segundos. Os botões opcionais mudam explicitamente o escopo ou a lista do grupo. Valores não recebidos de GS/CP aparecem como “—”. Desde a 0.1.13, CP vem da consulta oficial por nome e servidor para identidades locais e do grupo confirmadas na captura. É consultado em segundo plano a cada cinco minutos, com recuo após falhas e expiração em dez minutos; pode diferir temporariamente do jogo. A consulta não altera os totais de combate nem concede participação no grupo. O timer de berserk exige prazo confirmado e ainda não possui leitor validado nesta versão; não é inventado a partir de um prazo padrão.

O diagnóstico ao vivo recebeu dano e cura separados de um personagem local no espantalho. A leitura de aliados foi testada com mensagens controladas; falta comparação ao vivo em party. Mensagens de grupo incompletas ou homônimos sem servidor não autorizam personagens próximos. Entre no personagem com o app aberto para receber identidade e grupo; o jogo pode não reenviar esses registros ao abrir o app no meio da sessão. A cura representa os valores observados no tráfego, sem afirmar separação de overheal. A janela sobre tela cheia exclusiva e todos os cenários de múltiplos monitores ainda precisam de conferência no ambiente de uso.
