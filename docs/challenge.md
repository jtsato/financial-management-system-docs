# **Papel do Arquiteto de Soluções**  

O **Arquiteto de Soluções** é responsável por compreender e transformar requisitos de negócios, sejam eles **funcionais ou não funcionais**, em **capacidades e competências** que gerem valor para a organização.  

Suas principais responsabilidades incluem:  

- **Desenho de arquiteturas de contexto**, com a distribuição e responsabilidades dos processos e etapas, permitindo a segregação das capacidades;  
- **Capacidade analítica** para definir conceitos, processos e soluções que compõem a cadeia de valor da organização;  
- Tornar as soluções **escaláveis, reutilizáveis e flexíveis**, garantindo alinhamento com a estratégia de negócios e a arquitetura de referência;  
- **Definir estratégias de integração** entre áreas, atividades, serviços e sistemas, garantindo que juntos alcancem os resultados esperados no planejamento estratégico.  

---

# **Objetivo do Desafio**  

Desenvolver uma **arquitetura integrada** que otimize processos e sistemas, garantindo **valor para a organização**.  

## **Critérios principais:**  

- **Definição de contextos, capacidades de negócio e domínios funcionais**;  
- **Escalabilidade** das soluções para garantir **alta disponibilidade, segurança e desempenho**;  
- **Comunicação eficaz** entre áreas e serviços;  
- **Seleção adequada de padrões arquiteturais** e integração de tecnologias e frameworks;  
- **Otimização de requisitos não funcionais**;  
- **Criação de soluções flexíveis e reutilizáveis**.  

---

# **Aspectos Fundamentais**  

### **Compreensão dos Requisitos de Negócios**  
- O Arquiteto de Soluções deve entender profundamente os requisitos **funcionais e não funcionais** da organização e suas **capacidades necessárias** para gerar valor.  

### **Arquitetura Corporativa**  
- Definir **processos, etapas e responsabilidades** de forma isolada ou integrada, garantindo alinhamento com o contexto do negócio.  

### **Escalabilidade**  
- Garantir que a arquitetura suporte aumento de carga sem degradação de desempenho, utilizando:  
  - **Dimensionamento horizontal**,  
  - **Balanceamento de carga**,  
  - **Estratégias de cache**.  

### **Resiliência**  
- Projetar para **recuperação de falhas**, incluindo:  
  - **Redundância**,  
  - **Failover**,  
  - **Monitoramento proativo**,  
  - **Estratégias de recuperação**.  

### **Segurança**  
- Implementar **autenticação, autorização, criptografia** e proteção contra ataques.  

### **Padrões Arquiteturais**  
- Escolher o padrão adequado (**Microsserviços, Monolitos, SOA, Serverless**), considerando **trade-offs entre simplicidade e flexibilidade**.  

### **Integração**  
- Definir **protocolos, formatos de mensagem e ferramentas de integração**.  

### **Requisitos Não Funcionais**  
- Otimizar para **desempenho, disponibilidade e confiabilidade**, definindo métricas claras.  

### **Documentação**  
- Registrar **decisões arquiteturais, diagramas e fluxos de dados**, facilitando comunicação e manutenção.  

---

# **Descritivo da Solução**  

Um **comerciante precisa controlar seu fluxo de caixa diário** com lançamentos (**débitos e créditos**) e gerar um **relatório consolidado do saldo diário**.  

## **Requisitos de Negócio**  
✅ Serviço para controle de lançamentos  
✅ Serviço para consolidado diário  

## **Requisitos Obrigatórios**  
✔ Mapeamento de **domínios funcionais e capacidades de negócio**  
✔ Refinamento dos **requisitos funcionais e não funcionais**  
✔ Desenho completo da solução (**Arquitetura Alvo**)  
✔ Justificativa para a escolha de **ferramentas/tecnologias e arquitetura**  
✔ Implementação na **linguagem de preferência**  
✔ **Testes automatizados**  
✔ **README** com instruções claras sobre instalação e execução  
✔ **Hospedagem em repositório público (GitHub)**  
✔ Toda a **documentação do projeto** deve estar no repositório  

⚠ **Se os requisitos obrigatórios não forem atendidos, o teste será descartado.**  

---

# **Requisitos Diferenciais**  

- Desenho da solução para uma **Arquitetura de Transição** (se aplicável, considerando migração de legado);  
- **Estimativa de custos** com infraestrutura e licenças;  
- **Monitoramento e Observabilidade**;  
- Critérios de **segurança para consumo (integração) de serviços**.  

---

# **Requisitos Não Funcionais**  

- O serviço de **controle de lançamentos não pode ser impactado** caso o sistema de consolidado diário fique indisponível.  
- Em dias de pico, o serviço de consolidado diário recebe **50 requisições por segundo**, com **no máximo 5% de perda**.  

---

# **Observações**  

🔹 **Demonstre sua capacidade de tomada de decisão**, aplicando boas práticas e estruturando os componentes da solução.  
🔹 **Documente também o que você gostaria de ter implementado** e possíveis evoluções futuras.  
🔹 O tempo para execução do projeto é **limitado**, então utilize a documentação para **explicar suas escolhas** e demonstrar suas capacidades.  

🎯 **Boa sorte!** 🚀