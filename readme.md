# Projeto Completo: Integração de Apache NiFi, NiFi Registry e MinIO com Docker Swarm

## Introdução

Neste projeto, vamos criar um ambiente completo utilizando Docker Swarm para orquestrar contêineres do **Apache NiFi**, **Apache NiFi Registry** e **MinIO**. O objetivo é fornecer uma base sólida para você aprender sobre essas tecnologias, entendendo como elas interagem em um ambiente de cluster. Além disso, configuraremos o Apache NiFi para consumir dados de uma API pública existente e funcional, armazenando esses dados no MinIO.

## Tecnologias Utilizadas

- **Docker Swarm**: Orquestração de contêineres para criar um cluster distribuído.
- **Apache NiFi**: Plataforma para automação de fluxo de dados entre sistemas.
- **Apache NiFi Registry**: Ferramenta para versionamento e compartilhamento de fluxos de dados do NiFi.
- **MinIO**: Armazenamento de objetos compatível com S3, ideal para ambientes de nuvem privada.

## Pré-requisitos

- Docker instalado e configurado em sua máquina.
- Conhecimento básico de linha de comando.
- Acesso à internet para baixar as imagens dos contêineres.

## Sumário

1. **Inicializar o Docker Swarm**
2. **Criar uma Rede Overlay**
3. **Configurar o Arquivo `docker-compose.yml`**
4. **Implantar a Stack no Docker Swarm**
5. **Acessar os Serviços**
6. **Configurar o Fluxo de Dados no Apache NiFi**
7. **Consumir uma API Pública e Armazenar no MinIO**
8. **Configurar o Apache NiFi Registry**
9. **Escalar os Serviços (Opcional)**
10. **Limpeza dos Recursos**
11. **Considerações Finais**
12. **Próximos Passos**
13. **Referências**

##Referências

**Documentação do Apache NiFi v2** - https://nifi.apache.org/docs/nifi-docs/
**Processador InvokeHTTP** - https://nifi.apache.org/docs/nifi-docs/components/org.apache.nifi/nifi-standard-nar/1.15.3/org.apache.nifi.processors.standard.InvokeHTTP/
**Processador PutS3Object** - https://nifi.apache.org/docs/nifi-docs/components/org.apache.nifi/nifi-aws-nar/1.15.3/org.apache.nifi.processors.aws.s3.PutS3Object/
**JSONPlaceholder API** -
**Documentação do MinIO** -


