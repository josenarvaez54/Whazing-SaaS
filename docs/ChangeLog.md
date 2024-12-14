Versão 2.7.6.6
- bug - Gravacao Audio robotizado celular, troca lib grava espero resolva, aguardo feedback
- bug - Kanban some dados da tela alterados(valor, comentario) ao trocar lane
- bug - Relatorios contatos por estado não funcionava
- bug - alguns formatos arquivos recebidos nao mostrava legenda
- Geração PDF voltado modelo antigo e feito script excluir emojis, novo metodo não tava bom tambem
- Kanban alterado exibir lanes lado a lado
- Mensagens rapidas muito grandes truncar para não gerar tela enorme
- Envio arquivos tenta manter nome original do mesmo

Versão 2.7.6.5
- Suporte envio TXT

Versão 2.7.6.4 beta
- Separei busca tem campo novo buscar mensagens.. Busca contato junto mensagem não tava boa quando tem muita mensagem fica muito lenta
- Correção botão tela mensagem se mexer mouse ia canto tela

Versão 2.7.6.3 beta
- bug - Importar mensagem nao acionar bot interno e nem horario de atendimento

Versão 2.7.6.2 beta
- bug grave - Faz serviço travar caso excluir um usuario que esteja logado em algum local
- bug - notificação somando tickets fechados - filtro tickets status nao tava funcionando
- Bug da beta - Listagem erradas de tickets ainda
 - Validação para iniciar ticket pelos contatos evitar erro sem fila

Versão 2.7.6.1 beta
- Bug - Erro alterar usuario comum
- Bug - Melhoria geração pdf com conversas agora exibi emoticons(obs: deixou processo mais lento gerar pdf)

Versão 2.7.6 beta
- Bug versao beta - Campanha erro adicionar contatos
- Bug versão free - Listas filas nao atualizava corretamente versão free
- Bug - Contatos sem numeros fazendo da erro campanhas e outros relatorios
- Bug - Mais uma alteração filtros lista de atendimento para ver se melhora comportamento(não retornava ticket sem fila e atribuido ao usuario)
- Bug - Melhorias formatação textos vindo Typebot
- Delay 10s enceramento ticket pelo chatbot para garantir mensagem de enceramento seja entregue antes de fechar ticket
- Opção selecionar usuario online e offline hoje não tem uma utilidade decidir tirar para futuro talvez usar ela para alguma coisa util
- Mudança de cores padrões pelo painel SaaS
- Campanhas podem ser deletadas qualquer momento retirado validações
- Configuração para whazing não baixar mensagens que você envia por fora da prataforma(exemplo disparo pelo wasender, se cliente responder vai abrir o ticket)

Versão 2.7.5 beta

### Teve varias mudanças no kanban verificar configuração ####

- bug - problema formatação numeros causando erros conexoes hub - já que são contatos sem numeros
- Filtro na tela de agendamento pela data que foi agendado
- Chat interno aceita colar print no input
- Filtro LANE de contatos no KANBAN
- Edição lane kanban direto no contato
- Edição lane kanban direto na tela de antendimento
- Nas configurações tem 3 opções novas kanban uma para mostrar contatos tickets fechados, outra mostrar contatos sem fila atribuida e para deixar lanes ser compartilhados entre os usuarios e somente admin pode criar, editar e apagar lista de lanes.
- Tela atendimento mostra descrição informações adicionais tambem
- Tela atendimento mostra Valor negociação caso ela exista
- Opção "Reabrir tickets anteriores" alterada quando for criar ticket pela aba contatos tambem vai buscar tickets anteriores e reabre o mesmo

Versão 2.7.4 beta

- bug - importar historico de mensagem
- bug - tela atendimento modo celular não abre Dados de contato
- bug - Aumentado timeout para envio arquivos maiores edição de mensagens rapidas
- bug - Arquivos enviados pelo typebot não era exibidos corretamente no frontend
- bug - Enviar outros arquivos alem audio mostrava como gravando
- bug - Verificar nome do canal antes de cadastrar um HUB
- bug - Mensagens agendadas envia mesmo ticket fechado agora
- Cache grupos para melhor um pouco desempenho
- Validação se email já existe antes cadastrar nova empresa
- Validação se whatsapp já existe antes cadastrar nova empresa no teste
- Update versão varios pacotes como sequelize e outros
- Opção separada da quantidade tickets abertos e pedentes que carrega tela atendimento
- Permiti abrir ticket em conexão diferente para mesmo contato
- Suporte "instagram v2" do Hub notificame
- Opção Ignorar contato
- Maximo de usuarios e conexões vai respeitar o que esta no plano foi tirado da empresa
- Planos com opção para desativar acesso campanhas, integrações e grupos
- Suporte pagamento Stripe
- Filtro por tags na lista de atendimento
- Tags vem junto com tickets na lista de atendimentos para melhorar desempenho
- Carteiras vem junto com tickets na lista de atendimentos para melhorar desempenho
- Filtro para admin por usuario ou canal
- Hub caso não tenha nome "Name Unavailable" tenta atualizar nas próximas mensagens
- Arquivos Public separado por empresa
- Cache arquivos TypeBot - Sistema vai baixar arquivos e deixar salvo servidor não ter baixar cada vez que fluxo inicia melhorando velocidade e diminuindo consumo recursos
- Videos youtube colocados no Typebot seram baixados e colocados no cache

Versão 2.7.3

- bug - Mensagem duplicando chat interno
- bug - Chat interno depois de um certo numero de mensagens parava de listar
- bug - Consultar log de ticket
- bug - espiar ticket
- bug - Opção resolver ticket sem prescisar abrir ele
- bug - Configuração alterava de outras empresas com usuario SAAS
- bug - Mensagem vindas de story não chegava
- bug - Cadastro HUB respeitar limite de canais
- bug - conversas 2 empresas diferentes na mesma instalação não confirmava envio da mensagem
- Kanban (somente versão premium)
- Cadastro contato mais facil seleção pais vem brasil padrão não prescisa colocar 55
- Embelezamento numero telefone exibir br no lugar 55 e formatar numero
- Ao tentar abrir ticket caso já exista mostra nome do usuario ou fila para facilitar localização
- ChatFlow interno agora aceita transcrição de audio e reconhece caso cliente envie um arquivo
- Mudança 2 empresas diferentes podem usar mesmo nome de whatsapp
- Proporção videos e imagens tela chat melhorado a vizualização
- Melhoria notificações chat interno
- Configuração para desativar notificações de grupos
- Opção Reabrir tickets anteriores ao receber novas mensagens (Com essa opção ativada caso já exista ticket fechada ele vai abrir ele novamente e não criar um ticket novo.)
- Opção para selecionar hora tambem nas opção fechar e apagar ticket em Massa
- Opção deletar ticket individual na tela de atendimento( somente aparece admin)
- Baixar conversa - Ticket em PDF
- Colocado botão chamar whatsapp de suporte em pontos estrategicos(Tela inicial, tela solicitar teste, sesão whatsapp, financeiro, integrações e bot)
- Opção fechar ticket em massa e apagar foi mudada para dashboard
- Alterado tamanho campo Editar Mensagem na tela de atendimento
- Possibilidade alterar timezone pelo .env verificar arquivo example
- Trocada versao Baileys para usada pelo evolution

Versão: 2.6.0

- Suporte facebook e instagram  e WebChat via hub (função exclusiva versão premium)
- Melhorias de segurança socket
- Respeitar delay Typebot
- Deletar um canal definitivamente agora, antes somente ocultava conexão


Versão: 2.5.1

- bug - greeting nao tava mais funcionando
- bug - Erro criar contatos conflito entre empresas

Versão: 2.5.0

- bug - Clicar ticket pendente todas opções do topo estavam habilitadas
- bug - TypeBot e outras integrações aciona quando envia mensagem fora da prataforma
- bug - revisado opção deletar empresa para evitar erros
- bug - retornar ticket para fila limpa usuario
- bug - painel atendimento não mostra mais tickets fechados
- Pagina usuarios foi colocado exibir id para ser mais facil usar no TypeBot
- Integração  ChatGPT
- Integração Groq
- Integração Microsoft Azure Text-to-Speech
- Opção mensagem despedida personalizadas, pelo admin e pelos usuarios, admin pode criar, vizualizar e editar mensagens de todos usuarios,Usuarios somente podem acessar suas proprias mensagens 
- Mudança sistemas de variaveis e novas variaveis consultar arquivo pasta docs
- Opção escolher ocultar tabs ou não tela de atendimento
- ChatFlow opção enviar mensagem ao roteador para fila ou usuario
- Opção cadastro usuario para ignorar carteira mostrar todos contatos

Versão: 2.4.1

- Melhoria TypeBot caso transcrição audio estiver ativa transmite resultado para o typebot
- Novas opções TypeBot, transferir ticket, fechar ticket, colocar tag, parar ver arquivo docs


Versão: 2.4.0

- bug - botao enviar mensagem e audio tinha clicar lado meio nao funciona - obrigado Felipe
- bug - Ao clicar ticket nao exibia cor do canal e sem clicar nao exibia nome do usuario
- bug - Responder audio com transcrição perdia a resposta, pois fazia transcrição novamente
- Menu saas da empresa foi colocado opção para listar Faturas em aberto para apagar ou marcar como pagas
- Integração TypeBot
- Melhorias internas da integração baileys
- Alteração Menu para abrir descrição no computador - melhorias nesse menu pelo Felipe
- Alteração do Chat Interno e tela atendimento para tela cheia
- Novas configurações disponiveis .env, verifica .example da pasta backend

Versão: 2.3.5

- bug - não carregar alguns tickets
- bug - Não envia nome atentende aceitar ticket
- bug - ajustes (Admin) - Visualizar Todos para melhor funcionamento
- Separado opção quantidades tickets abertos/pedentes e fechados carregar tela de atendimento
- Escolha cor canal para diferenciar tela atendimento
- Botão reniciar as conexões no canais
- Colocando sistema simular digitando e gravando audio para tornar atendimento mais humano
- Suporte WebHook - N8N

Versão: 2.3.4

- Bug Assas - Cada vez gerava link novo agora usa o mesmo
- Bug - Lista de contatos não carregava as etiquetas
- Tirado coluna instagram e telegram tela contatos ficar mais limpa
- Sistema de envio mensagem ao aceitar ticket e transferir ticket foi remodelado, as configurações agora são nos canais e será possivel personalizar mensagens
- Botão resolver ticket na lista de tickets
- Busca tela atendimento busca mensagens tambem
- Envio de reações
- Configuração para bloquear usuarios reabrir tickets fechados(Podem consultar mas não reabrir o mesmo)
- Opção contatos para desativar bot ou campanha
- Ajuste para exibir mensagem de erro ao tentar cadastrar contato sem ter whatsapp conectado

Versão: 2.3.3

- Bug cadastra empresa pelo painel sem CNPJ
- Bug limite 40 usuarios alterar grupos chat interno
- Silencioso não desativava

Versão: 2.3.2

- Suporte Asaas
- Retirada campo CNPJ tela solicitar teste e Validação campos
- Tela SaaS campo cnpj passa a ser opcional
- Ao cadastra teste na pagina solicitação redireciona para pagina login

Versão: 2.3.1

- bug - adicionar novo canal nao aceitava

Versão: 2.3.0

- outros pequenos bugs
- bug - Tela canais e atendimento listar mais de 40 usuários
- bug - tarefa mesmo concluida aparecia ainda na notificações
- bug - ajustes planos aceita planos com virgula no preço
- Configuração mercado pago foi colocado detalhes do webhook
- Atualização libs do backend e do frontend
- Remoção conteudos não usados/defasados
- Colocado Logo nos relatorios gerar impressão
- Opção tirar som das notificações
- Variveis adicionadas ({{user}}, {{phoneNumber}}, {{email}})
- Novas configurações do banco de dados (para ajustes desempenho) via .env
- Ajustes chaves para performace baileys
- Exibir horario na lista de agendamentos
- Sistema de avalição
- Transcrição de audio
- Configuração para quantidade tickets carregar tela atendimento(padrão 30)
- Tela atendimento abas (Aberto, pedentes, fechados e bots aparece somente se tiver tickets) - mudado no filtro texto resolvidos para fechados para seguir mesmo padrão
- Tela atendimento botão carregar mais tickets

Versão: 2.2.5

- Atualização emergencia - Update lib não oficial baileys

Versão: 2.2.4

- Update lib não oficial baileys
- Totalmente remodelado sistema importar mensagens ao ler QRCODE
- Detectar mensagem apagada pelo contato
- Integração com Mercado Pago

Versão: 2.2.3

- Modulos tarefas
- Bug envio audio IPHONE
- Bug painel escutar audio IPHONE
- Bug não tava exibindo mais de 40 usuarios
- Correção outros pequenos bugs

Versão: 2.2.2

- Caso desabilitar smtp ou opção solicitar teste agora botão esqueci senha e registre-se agora sai da pagina login
- Correção erro na API
- Envia mensagem para whatsapp cadastrar teste(caso whatsapp seja invalido não vai aceitar cadastrar teste)
- Novas apis mostrar informação do Ticket, mostrar tickets no chatbot, mostrar todos tickets, troca de etiquetas, troca de filas, envio mensagens via metodo GET, alterar status ticket
- Correção outros pequenos bugs

Versão: 2.2.1

- Correção geração protocolo, somente gerar quando solicitado
- Opção caso atendente demorar responder voltar ticket para Pedentes
- Correção opção autoclose não estava funcionando
- Nova opção flow para bot enviar mensagem depois tempo caso cliente não responder
- Ajuste menu lateral flow
- Opção flow quando cliente manda mensagem fora do horario de atendimento o que fazer aquele ticket
- Opção para colocar numero vezes bot deve enviar mensagem de fora horairo de atendimento
- Correção erro obter carteira, tags
- Melhoriar no MODO DARK
- Opção de baixar Fluxo e importar Fluxo
- Correção outros pequenos bugs