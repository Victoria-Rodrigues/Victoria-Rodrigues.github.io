# MySQL HeatWave como base de conhecimento do OCI AI Agent

## 📌 Introdução

Neste laboratório, você será guiado passo a passo no processo de configuração de uma base de conhecimento para Oracle Generative AI Agents, integrando fontes armazenadas no Object Storage e no banco de dados MySQL HeatWave.

<br>

### 📌 **Objetivos**

Descubra como realizar de forma prática a criação, configuração e utilização do MySQL Heatwave e suas funcionalidades de Generative AI.

Pré-requisitos:

- Conta de avaliação gratuita da Oracle.
- Uma instância funcional do MySQL HeatWave com o Lakehouse habilitado.
- Uma conexão OCI Database Tools configurada para acessar sua instância do HeatWave (veja no passo 5️⃣)
- Um agente de IA criado e configurado, caso este passo ainda não tenha sido realizado, volte à **Etapa 2: Criação e configuração do AI Agent**

<br>


## 1️⃣ Criação de uma base de conhecimento HeatWave para o Agente de IA

Uma base de conhecimento HeatWave utiliza a capacidade de busca vetorial da sua instância MySQL HeatWave. Primeiro, você precisa criar um procedimento armazenado de busca contextual na sua instância MySQL HeatWave, que será chamado pelo Agente de IA ao recuperar o contexto. Em seguida, você pode criar uma base de conhecimento e configurá-la para se conectar à sua instância MySQL HeatWave e usar o procedimento de busca contextual.

## ## 1️⃣.1️⃣ Criação do procedimento de busca contextual

## 2️⃣ Criar banco de dados MySQL

No console, clique em **Menu de navegação > Databases > DB Systems**.

![Menu DB Systems](images/MySQL01.png)


Clique em **Create DB System**.

Como se trata de experimentação, escolha Desenvolvimento ou Teste .

Verifique o compartimento; ele deve ser o mesmo compartimento em que você criou a VCN e atribua um nome ao sistema de banco de dados

![Criação do DB Systems](images/MySQL02.png)

Na seção **Create administrator credentials**, insira o nome de usuário e escolha uma senha, mas certifique-se de anotá-la, pois você a usará mais tarde

Na **Setup** , selecione **Standalone** .

Em **Configure Netwrok**, certifique-se de selecionar a mesma VCN e a mesma subnet privada criada anteriormente.

![Criação do DB Systems](images/MySQL03.png)

Confirme se na seção **Configure hardware** a opção **Enable HeatWave cluster** está habilitada. 

Altere o shape do MySQL para **MySQL.16**.

![Criação do DB Systems](images/MySQL04.png)

Clique em **Configure HeatWave cluster** e, em seguida, clique em **Change Shape**.

Selecione **HeatWave.512GB** e clique em **Select a shape**.

![Criação do DB Systems](images/MySQL05.png)

Atualize os nós para **2**.

![Criação do DB Systems](images/MySQL06.png)

Na seção **Storage size** atualize o **Initial data storage size (GB)** para **1024**.

![Criação do DB Systems](images/MySQL07.png)

Na seção **Configure backup plan**, mantenha a janela de backup padrão de 7 dias. Desative a opção **Enable point-in-time recovery**.

![Criação do DB Systems](images/MySQL08.png)

Deslize a tela para baixo e clique em **Show advanced option**.

![Criação do DB Systems](images/MySQL09.png)

Acesse a aba **Connections** e insira o seguinte:

Hostname: mysql-lakehouse

Database port: 3306

Database X protocol port: 33060

Após concluir, clique em **Create**.

![Criação do DB Systems](images/MySQL10.png)

O sistema de banco de dados MySQL estará no estado **CREATING**.

![Criação do DB Systems](images/MySQL11.png)

## 👥 Agradecimentos

- **Autores** - Julio Rocha
- **Última Atualização Por/Data** - Novembro 2025

## 🛡️ Declaração de Porto Seguro (Safe Harbor)

O tutorial apresentado tem como objetivo traçar a orientação dos nossos produtos em geral. É destinado somente a fins informativos e não pode ser incorporado a um contrato. Ele não representa um compromisso de entrega de qualquer tipo de material, código ou funcionalidade e não deve ser considerado em decisões de compra. O desenvolvimento, a liberação, a data de disponibilidade e a precificação de quaisquer funcionalidades ou recursos descritos para produtos da Oracle estão sujeitos a mudanças e são de critério exclusivo da Oracle Corporation.

Esta é a tradução de uma apresentação em inglês preparada para a sede da Oracle nos Estados Unidos. A tradução é realizada como cortesia e não está isenta de erros. Os recursos e funcionalidades podem não estar disponíveis em todos os países e idiomas. Caso tenha dúvidas, entre em contato com o representante de vendas da Oracle. 
