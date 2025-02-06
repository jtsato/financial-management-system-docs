# **ADR 001: Escolha da Arquitetura de Microsserviços para o Sistema de Fluxo de Caixa**

## **Status**: ✅ Aprovado

## **Contexto**  
O sistema de fluxo de caixa para comerciantes requer alta escalabilidade, resiliência e desempenho para lidar com um grande volume de transações financeiras. O sistema deve ser capaz de registrar lançamentos (débitos e créditos) e consolidar saldos diários de forma eficiente, garantindo consistência e disponibilidade. Além disso, é necessário suportar picos de requisições e fornecer monitoramento e observabilidade para garantir a saúde do sistema.

## **Decisão**  
Adotar uma **arquitetura de microsserviços** com os seguintes componentes principais:  
1. **Serviço de Lançamentos**: Responsável por registrar e gerenciar transações financeiras.  
2. **Serviço de Consolidação**: Responsável por calcular e armazenar saldos diários consolidados.  
3. **API Gateway**: Centraliza e roteia requisições para os serviços.  
4. **Fila de Mensagens (Kafka)**: Garante comunicação assíncrona e resiliência entre serviços.  
5. **Monitoramento e Logging**: Utiliza o LGTM Stack (Loki, Grafana, Tempo, Mimir) para observabilidade.  

As tecnologias escolhidas incluem:  
- **React** para a interface do usuário.  
- **C# .NET Core** para desenvolvimento de APIs.  
- **PostgreSQL** para persistência de transações.  
- **MongoDB** para armazenamento otimizado de saldos consolidados.  
- **Kafka** para filas de mensagens.  
- **Docker + Kubernetes** para orquestração de containers.  

## **Consequências**  
### **Vantagens**  
- **Escalabilidade**: Cada serviço pode ser escalado independentemente, atendendo a picos de demanda.  
- **Resiliência**: Falhas em um serviço não impactam outros serviços (ex.: falha no Serviço de Consolidação não afeta o Serviço de Lançamentos).  
- **Desenvolvimento Independente**: Equipes podem trabalhar em serviços diferentes sem interferências.  
- **Tolerância a Falhas**: A fila de mensagens (Kafka) garante que eventos sejam processados mesmo em caso de falhas temporárias.  

### **Desvantagens**  
- **Complexidade**: Gerenciar microsserviços exige ferramentas e práticas adicionais (ex.: orquestração com Kubernetes, monitoramento distribuído).  
- **Latência**: Comunicação entre serviços pode introduzir latência adicional.  
- **Custos Operacionais**: Manter múltiplos serviços e infraestrutura pode ser mais caro.  

### **Riscos**  
- **Sincronização de Dados**: Garantir consistência entre serviços pode ser desafiador.  
- **Monitoramento Distribuído**: Requer ferramentas robustas para rastrear requisições entre serviços.  

## **Alternativas Consideradas**  
### **1. Arquitetura Monolítica**  
- **Vantagens**: Simplicidade no desenvolvimento e deploy.  
- **Desvantagens**: Dificuldade para escalar, maior acoplamento e impacto de falhas em todo o sistema.  

### **2. Arquitetura Baseada em Eventos**  
- **Vantagens**: Maior desacoplamento e escalabilidade.  
- **Desvantagens**: Complexidade adicional para garantir consistência e rastreabilidade.  

## **Decisão Final**  
A arquitetura de microsserviços foi escolhida por atender melhor aos requisitos de escalabilidade, resiliência e desempenho. Apesar da complexidade adicional, os benefícios superam os custos, especialmente considerando o volume de transações e a necessidade de alta disponibilidade.  
