# Regras do projeto Daeva Nexus

Ao criar uma função independente que possa ser ativada/desativada, integre-a à tela Módulos na mesma alteração. Cadastre seu cartão em ModulesViewModel, estenda ModuleSettings/ModuleId com padrão compatível com arquivos antigos e conecte ativação, desativação e inicialização ao funcionamento real da função. Acrescente testes de desligamento, reativação e persistência. Não acrescente cartões de funções ainda inexistentes nem botões sem ação implementada.

Desativar um módulo deve preservar dados e preferências anteriores, impedir seu trabalho funcional em segundo plano e manter os serviços compartilhados necessários aos demais módulos. Identificação básica, perfil do personagem e atualização do aplicativo são serviços comuns. Não confunda ocultar uma janela com desativar a função. Mantenha o tema cinza chumbo e azul e os estados acessíveis por teclado.
