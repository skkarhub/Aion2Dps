# Daeva Nexus

O projeto foi refeito do zero e passa a se chamar **Daeva Nexus**. Esta é a nova base do aplicativo Windows, na versão 0.1.3 alpha.

O menu **Início** reúne o cartão do personagem (nome, classe, nível e retrato) e a seção **Sua rotina**, com atividades diárias, semanais e recursos separados por personagem.

A rotina permite ver o personagem atual, selecionar outro já identificado ou exibir todos. **Não perca** destaca recursos cheios; **Falta fazer** mostra atividades com leitura disponível; **Dados indisponíveis** mantém visível o que ainda não pôde ser lido. Os dados ficam salvos neste PC, por nome e servidor, em `%LOCALAPPDATA%/DaevaNexus/activities.json`. Personagens desconectados mostram a última leitura, e valores vencidos após o reset aguardam nova confirmação do jogo.

Foram conferidos ao vivo Shugo (9 normais e 5 extras), Pesadelo (entradas normais e extras separadas), Rito de Ascensão, tempo no Abismo, a passagem de zero para uma Missão de Dever concluída e a compra de Energia de Od na Associação Brisa (20/20, com reset enviado pelo servidor). No teste, o contador da loja chegou após reabrir completamente o jogo; a seleção de personagens e a troca de abas não o reenviaram. Leituras de loja confirmadas são preservadas ao receber uma nova lista de entradas, até seu prazo de validade ou atualização explícita. A compra de Pedras da Fenda do Piso Inferior do Abismo (7D), na Associação Brisa, também foi validada ao vivo em 2/7, por personagem; essa oferta é temporária e tem reset informado pelo servidor. Os sete cartões de Kinah, presença, corredores, suprimentos e crafts ficam ocultos enquanto a leitura automática não é implementada; as definições foram preservadas para uma etapa futura. Não há preenchimento manual nem conclusão presumida. Os horários desta versão para América do Sul usam 04h de Brasília diariamente e quarta-feira para o reset semanal.

O banner adapta nome, identificação, bordas e fundo à classe do personagem. Quando o serviço demora a entregar o retrato, há novas tentativas automáticas em 15, 30 e 60 segundos; depois o intervalo retorna a cinco minutos. A disponibilidade depende do serviço público. Uma atualização temporariamente sem imagem preserva o retrato do mesmo personagem, enquanto a troca de personagem limpa a imagem anterior.

## Executar

Baixe `DaevaNexus-Setup-0.1.3.exe` na seção Releases. O assistente permite escolher a pasta e criar um atalho na área de trabalho. O aplicativo aparece na lista de aplicativos instalados do Windows. O instalador é por usuário e não instala o Npcap automaticamente.

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
