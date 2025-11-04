# MySQL HeatWave como base de conhecimento do OCI AI Agent

## 📌 Introdução

EsNeste laboratório, você preparará a infraestrutura necessária para executar o restante do workshop. Criaremos/configuraremos os seguintes elementos: uma Rede Virtual em Nuvem, o Banco de Dados MySQL e o Cluster HeatWave.

<br>

### 📌 **Objetivos**

Descubra como realizar de forma prática a criação, configuração e utilização do MySQL Heatwave e suas funcionalidades de Generative AI.

O que você aprenderá:

- Crie uma VCN (Virtual Cloud Network) que ajude você a definir sua própria topologia de rede de data center dentro da Oracle Cloud.
- Crie o próprio banco de dados MySQL.
- Ative o cluster analítico do Heatwave.

Pré-requisitos:

- Conta de avaliação gratuita da Oracle.

<br>


## 1️⃣ Crie uma Rede Virtual na Nuvem e permita o tráfego pela porta do Serviço de Banco de Dados MySQL.  

> **ATENÇÃO: Certifique-se de estar na região US Midwest (Chicago)**

Faça login em seu tenant do OCI. No **menu de navegação**, selecione **Networking > Virtual cloud networks**.

![Open VCN](images/VCN01.png)


Selecione seu compartimento na lista e clique em **Start VCN Wizard**.
> **Observação: Se você não selecionou um compartimento, pode selecionar o compartimento raiz, que foi criado por padrão quando você criou sua tenancy (ou seja, quando se registrou para a conta de avaliação). É possível criar tudo no compartimento raiz, mas a Oracle recomenda que você crie subcompartimentos para ajudar a gerenciar seus recursos com mais eficiência.**

![VCN Wizard](images/VCN02.png)


Selecione **Create VCN with Internet Connectivity** e clique em **Start VCN Wizard**.

![VCN Wizard Internet](images/VCN03.png)


No campo **VCN Name**, insira um nome para esta VCN e certifique-se de que o compartimento selecionado seja o correto. Mantenha as configurações padrão e clique em **Next**.

![VCN Wizard - VCN Name](images/VCN04.png)


Analise as informações e clique em **Create**.

![VCN Wizard - Create](images/VCN05.png)


Após a criação da VCN, em **Subnets**, clique em **private subnet-< nome da VCN >**.

![VCN Config - Subnet Private Network](images/VCN06.png)


Personalize a lista de segurança padrão da VCN para permitir o tráfego pelas portas do serviço de banco de dados MySQL clicando em **security list for private subnet-< nome da VCN >**.

![VCN Config - Security List](images/VCN07.png)


Em **Security rules**, clique em **Add Ingress Rules**.

![VCN Config - Ingress Rules](images/VCN08.png)

Adicione a regra necessária à lista de segurança padrão para permitir o tráfego pela porta do serviço MySQL HeatWave e clique em **Add Ingress Rules**.

Source CIDR:

    0.0.0.0/0

Destination Port Range: 

    3306, 33060

Description:

    MySQL Ports

![VCN Config - Add Ingress Rules](images/VCN09.png)


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
