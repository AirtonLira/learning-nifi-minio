Docker Compose: Apache NiFi + Schema Registry + MinIO
Este repositório contém a configuração do Docker Compose para criar um ambiente de desenvolvimento local com Apache NiFi, Schema Registry e MinIO, todos configurados com volumes persistentes.
📋 Pré-requisitos

Docker instalado
Docker Compose instalado
Mínimo de 4GB de RAM disponível
Portas 8443, 8081, 9000 e 9001 disponíveis

🚀 Serviços Incluídos
Apache NiFi

Interface web para automação e gerenciamento de fluxo de dados
Porta: 8443 (HTTPS)
Credenciais padrão: admin/adminadmin

Schema Registry

Gerenciamento de schemas para dados estruturados
Porta: 8081

MinIO

Armazenamento de objetos compatível com S3
Porta API: 9000
Porta Console Web: 9001
Credenciais padrão: minioadmin/minioadmin

📁 Estrutura do Projeto
Copy.
├── docker-compose.yml
└── README.md
💾 Volumes Persistentes
NiFi

nifi_conf: Configurações
nifi_content: Repositório de conteúdo
nifi_database: Banco de dados
nifi_flowfile: Repositório de FlowFiles
nifi_provenance: Repositório de proveniência
nifi_state: Estado

Schema Registry

schema_registry_data: Dados do registry

MinIO

minio_data: Dados do objeto store

🔧 Instalação e Execução

Clone este repositório:

bashCopygit clone <seu-repositorio>
cd <seu-repositorio>

Inicie os serviços:

bashCopydocker-compose up -d

Verifique se todos os containers estão rodando:

bashCopydocker-compose ps
🌐 Acessando os Serviços
Apache NiFi

URL: https://localhost:8443/nifi
Usuário: admin
Senha: adminadmin

Schema Registry

URL: http://localhost:8081

MinIO Console

URL: http://localhost:9001
Usuário: minioadmin
Senha: minioadmin

🛑 Parando os Serviços
Para parar todos os serviços mantendo os dados:
bashCopydocker-compose down
Para parar e remover todos os volumes (⚠️ isso apagará todos os dados):
bashCopydocker-compose down -v
🔍 Logs e Monitoramento
Ver logs de todos os serviços:
bashCopydocker-compose logs
Ver logs de um serviço específico:
bashCopydocker-compose logs [nifi|schema-registry|minio]
🔄 Reiniciando Serviços
Reiniciar um serviço específico:
bashCopydocker-compose restart [nifi|schema-registry|minio]
🌡️ Verificação de Saúde
NiFi
bashCopycurl -k https://localhost:8443/nifi
Schema Registry
bashCopycurl http://localhost:8081/subjects
MinIO
bashCopycurl http://localhost:9000/minio/health/live
⚠️ Considerações de Segurança

As credenciais fornecidas são para desenvolvimento. Em produção, use senhas fortes
O NiFi está configurado com HTTPS, mas usa um certificado auto-assinado
Considere adicionar autenticação adequada em ambiente de produção
Revise as políticas de rede antes de expor os serviços externamente

🛠️ Customização
Para customizar as configurações, você pode:

Modificar as variáveis de ambiente no docker-compose.yml
Ajustar as portas mapeadas
Modificar os volumes conforme necessário
Adicionar novos serviços à stack

📝 Notas Adicionais

Os dados são persistidos mesmo após parar os containers
Primeira inicialização pode levar alguns minutos
Verifique os requisitos de memória e CPU se encontrar problemas de performance

🤝 Contribuindo

Faça um Fork do projeto
Crie sua Feature Branch (git checkout -b feature/AmazingFeature)
Commit suas mudanças (git commit -m 'Add some AmazingFeature')
Push para a Branch (git push origin feature/AmazingFeature)
Abra um Pull Request