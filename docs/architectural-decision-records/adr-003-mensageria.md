# **ADR 003: Utilização de Kafka para Comunicação Assíncrona**

## **Status**: ✅ Aprovado

## **Contexto**  
A comunicação entre o **Serviço de Lançamentos** e o **Serviço de Consolidação** deve ser resiliente e tolerante a falhas.  

## **Decisão**  
Utilizar **Apache Kafka** como fila de mensagens para garantir comunicação assíncrona e resiliência.  

## **Consequências**  
### **Vantagens**  
- **Resiliência**: Mensagens são armazenadas e processadas mesmo em caso de falhas.  
- **Escalabilidade**: Kafka é altamente escalável e suporta alto volume de mensagens.  

### **Desvantagens**  
- **Complexidade**: Configuração e gerenciamento de Kafka exigem conhecimento especializado.  
- **Latência**: Comunicação assíncrona pode introduzir latência.  

## **Alternativas Consideradas**  
### **1. Comunicação Síncrona (HTTP/REST)**  
- **Vantagens**: Simplicidade na implementação.  
- **Desvantagens**: Falhas no Serviço de Consolidação impactariam o Serviço de Lançamentos.  

### **2. Outras Filas de Mensagens (RabbitMQ)**  
- **Vantagens**: Mais simples de configurar.  
- **Desvantagens**: Menos escalável que Kafka.  

## **Decisão Final**  
Kafka foi escolhido por sua escalabilidade e tolerância a falhas, garantindo que os eventos de lançamentos sejam processados mesmo em cenários de falha.  
