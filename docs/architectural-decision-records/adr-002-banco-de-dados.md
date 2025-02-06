# **ADR 002: Escolha de Banco de Dados Relacional para Transações e NoSQL para Consolidação**

## **Status**: ✅ Aprovado

## **Contexto**  
O sistema precisa armazenar dois tipos principais de dados:  
1. **Transações Financeiras**: Requer consistência e atomicidade.  
2. **Saldos Consolidados**: Requer consultas rápidas e escalabilidade.  

## **Decisão**  
Utilizar:  
- **PostgreSQL** para o **Serviço de Lançamentos**, garantindo consistência e suporte a transações.  
- **MongoDB** para o **Serviço de Consolidação**, permitindo consultas rápidas e escalabilidade horizontal.  

## **Consequências**  
### **Vantagens**  
- **PostgreSQL**: Garante consistência e atomicidade nas transações financeiras.  
- **MongoDB**: Oferece desempenho superior para consultas de saldos consolidados.  

### **Desvantagens**  
- **Complexidade**: Gerenciar dois bancos de dados diferentes aumenta a complexidade operacional.  
- **Sincronização**: Requer mecanismos para garantir que os dados estejam sincronizados entre os serviços.  

## **Alternativas Consideradas**  
### **1. Utilizar Apenas PostgreSQL**  
- **Vantagens**: Simplicidade no gerenciamento de um único banco de dados.  
- **Desvantagens**: Desempenho inferior para consultas de saldos consolidados.  

### **2. Utilizar Apenas MongoDB**  
- **Vantagens**: Desempenho superior para consultas.  
- **Desvantagens**: Dificuldade em garantir consistência nas transações financeiras.  

## **Decisão Final**  
A combinação de PostgreSQL e MongoDB foi escolhida para atender às necessidades específicas de cada domínio, garantindo consistência nas transações e desempenho na consolidação.  
