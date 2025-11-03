# Introdução

## Sobre o workshop

A adoção de inteligência artificial generativa nas empresas está revolucionando a maneira como organizações **automatizam processos** e aprimoram a experiência do cliente. No centro dessa transformação estão os agentes virtuais baseados em IA, projetados para interagir com usuários, entender solicitações em linguagem natural, executar tarefas e fornecer respostas contextualizadas de acordo com seus dados de forma **autônoma e personalizada**.

O serviço de **OCI Generative AI Agents** oferece uma solução totalmente gerenciada na Oracle Cloud Infrastructure (OCI) que aproveita poder dos Large Language Models (LLMs) para criar agentes virtuais **altamente eficientes** e aliados com a **modernização do atendimento e processos**.

Alguns recursos interessantes sobre o serviço:

- **Integração de dados e canais de interação:** Suporte a chat e API, facilitando a interação entre usuários e agentes.  
- **Respostas contextualmente relevantes:** As respostas são geradas com base em consultas inteligentes à base de conhecimento, garantindo precisão e contexto.  
- **Pesquisa híbrida:** Combina métodos léxicos e semânticos para alcançar maior assertividade nas respostas.  
- **Moderação de conteúdo:** Garante interações seguras e respeitosas com controles para entrada e saída de dados.  
- **Conversas multi-turn:** Permite que usuários façam perguntas de acompanhamento, com respostas que levam em conta o histórico da conversa.  
- **Interpretação de elementos visuais:** Capacidade de interpretar gráficos e tabelas em PDFs sem necessidade de descrições adicionais.  
- **Hiperlinks automáticos:** Os links presentes nos documentos são automaticamente extraídos e incluídos nas respostas.  

Dependendo do caso de uso, você pode adicionar a cada agente as seguintes ferramentas:

- **SQL Tool**: Transforma comandos de linguagem natural em consultas SQL para extração de dados nos bancos conectados.

- **RAG Tool**: Recupera informações de uma ou mais bases de conhecimento para obter os melhores contexto para suas respostas utilizando linguagem natural.

- **Agent Tool**: Orquestra uma rede de multi-agentes especializados, colaborando na execução de tarefas mais complexas.

- **Custom Function Calling Tool**: Permite ao agente acionar funções definidas pelo usuário, expandindo as possibilidades de automação e resposta de acordo com as necessidades do negócio.

- **Custom API Endpoint Calling Tool**: Integra facilmente com APIs da OCI ou REST APIs customizadas, garantindo muito mais conectividade e flexibilidade.

Para mais informações sobre o serviço acesse a documentação:[Generative AI Agents](https://docs.oracle.com/en-us/iaas/Content/generative-ai-agents/home.htm)

### **Objetivos**

Neste laboratório, vamos explorar a utilização do OCI Generative AI Agent em conjunto com a ferramenta RAG. A técnica de RAG permite que o **agente recupere informações em suas bases de dados**, fornecendo **contextos relevantes e atualizados** para a reformulação das respostas finais. Essa integração aprimora significativamente a atuação dos chatbots, tornando-os capazes de oferecer **respostas mais precisas, contextualizadas e alinhadas** aos dados reais da organização.

O conjunto de dados acessado pelo agente é denominado **base de conhecimento**. Neste laboratório, utilizaremos o **Object Storage** e o **MySQL HeatWave** como fontes dessa base. O Object Storage permite armazenar documentos, arquivos e conteúdos estruturados ou não estruturados. Já o MySQL HeatWave é o único serviço MySQL totalmente gerenciado que combina funcionalidades de transações, análises, aprendizado de máquina e serviços GenAI. Vamos explorar como utilizar o armazenamento vetorial do MySQL HeatWave para compor a base de conhecimento, potencializando ainda mais a precisão e a riqueza das respostas fornecidas pelos agentes.


![Buckets](images/fluxo-ai-agent.png)


<br>

### **O que você vai aprender?**

- Criação de um bucket e upload dos arquivos.
- Criação da instância do MySQL Heatwave e configuração da base vetorizada.
- Criação do Agent.
- Criação e configuração da base de conhecimento no Agente.
- Acessar e testar o agente. 


<br>

### **Pré-requisitos**

Este laboratório pressupõe que você tenha:

- Uma conta Oracle Cloud
- Acesso a uma região onde o serviço de agente está disponível: **Ashburn, São Paulo, Frankfurt, Osaka, London, Chicago e Phoenix.** [Lista das regiões disponíveis](https://docs.oracle.com/en-us/iaas/Content/generative-ai-agents/overview.htm#regions) 
- Deve ter uma conta de administrador ou permissões para gerenciar alguns serviços da OCI: Policies, Generative AI Agents, Object Storage e MySQL Heatwave.    

<br>

## 👥 Agradecimentos

- **Autores** - Victória Rodrigues
- **Autores Contribuintes** - Isabelle Anjos
- **Última Atualização Por/Data** - Outubro 2025

## 🛡️ Declaração de Porto Seguro (Safe Harbor)

O tutorial apresentado tem como objetivo traçar a orientação dos nossos produtos em geral. É destinado somente a fins informativos e não pode ser incorporado a um contrato. Ele não representa um compromisso de entrega de qualquer tipo de material, código ou funcionalidade e não deve ser considerado em decisões de compra. O desenvolvimento, a liberação, a data de disponibilidade e a precificação de quaisquer funcionalidades ou recursos descritos para produtos da Oracle estão sujeitos a mudanças e são de critério exclusivo da Oracle Corporation.

Esta é a tradução de uma apresentação em inglês preparada para a sede da Oracle nos Estados Unidos. A tradução é realizada como cortesia e não está isenta de erros. Os recursos e funcionalidades podem não estar disponíveis em todos os países e idiomas. Caso tenha dúvidas, entre em contato com o representante de vendas da Oracle. 