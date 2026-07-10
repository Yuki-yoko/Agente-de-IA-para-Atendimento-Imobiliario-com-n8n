# Agente de IA para Atendimento Imobiliário com n8n

Sistema de automação desenvolvido no **n8n** utilizando **Google Gemini** para automatizar o atendimento de clientes interessados em imóveis.

<img width="755" height="378" alt="image" src="https://github.com/user-attachments/assets/282cef67-d613-4aaf-a583-881b610e4571" />

O fluxo recebe e-mails automaticamente, interpreta a solicitação do cliente utilizando Inteligência Artificial, pesquisa imóveis disponíveis em uma planilha do Google Sheets, realiza agendamentos ou reagendamentos de visitas e responde ao cliente de forma automática por e-mail.

---

# Funcionalidades
<img width="1047" height="414" alt="image" src="https://github.com/user-attachments/assets/5fc32508-a7c0-4d43-b144-688c93fa1246" />

- Recebimento automático de e-mails via Gmail;
- Interpretação da solicitação do cliente utilizando IA;
- Pesquisa de imóveis disponíveis conforme o perfil informado;
- Agendamento de visitas aos imóveis ou Reagendamento de visitas;
- Registro e atualização dos dados dos clientes em uma planilha;
- Respostas automáticas por e-mail.

---

# 🛠️ Tecnologias Utilizadas

- n8n
- Google Gemini
- Gmail
- Google Sheets
---

# Funcionamento

## 1. Trigger Gmail

O fluxo inicia quando um novo e-mail é recebido na conta Gmail.

---

## 2. Agente de IA

O AI Agent recebe o corpo do e-mail do cliente juntamente com um prompt contendo todas as instruções necessárias para o atendimento.

O agente é responsável por:

- Interpretar a solicitação do cliente;
- Identificar o perfil do imóvel desejado;
- Consultar a planilha de imóveis;
- Agendar ou reagendar visitas;
- Gerar uma resposta personalizada.

No AI Agent é utilizado um prompt que orienta toda a lógica de funcionamento da automação.

---

## 3. Integração com Google Sheets

A automação utiliza duas planilhas.

### Planilha de Imóveis

Essa planilha contém todos os imóveis cadastrados pela imobiliária.

Sempre que um cliente solicita um imóvel, o agente consulta essa planilha para localizar apartamentos compatíveis com as características informadas.

---

### Planilha de Agendamentos

Essa planilha é utilizada para armazenar os dados dos clientes que desejam agendar ou reagendar uma visita.

O funcionamento é o seguinte:

- Caso o e-mail do cliente ainda não exista na planilha, uma nova linha é criada;
- Caso o cliente já esteja cadastrado, suas informações são atualizadas.

O e-mail é utilizado como identificador único do cliente.

---

# Importante

Os nomes das ferramentas (Tools) cadastradas no AI Agent devem ser exatamente iguais aos nomes utilizados no prompt.

Caso os nomes sejam diferentes, a IA não conseguirá localizar corretamente as ferramentas e acessar as planilhas.

---

# 4. Envio do E-mail

Após interpretar a solicitação do cliente e consultar as planilhas necessárias, o Agente de IA gera automaticamente uma resposta personalizada.

Em seguida, essa resposta é enviada ao cliente através do Gmail.

---

# Estrutura do Projeto

```
📁 Projeto
.
├── AgenteIAImobiliario.json          # Workflow completo do n8n
├── Prompt.pdf             # Prompt utilizado pelo agente imobiliário
├── Agenda.xlsx            # Planilha utilizado para o agendamento
├── BaseApartametos.xlsx   # Planilha com todos os apartamentos disponíveis na empresa
└── README.md

```
---
# Exemplo de Funcionamento

### E-mail recebido
A imobiliária recebe esse e-mail:
<img width="1125" height="343" alt="image" src="https://github.com/user-attachments/assets/a433de06-ec7f-48c9-a069-7d3c3e903538" />


### As preferencias do cliente são verificados na planilha (BaseApartamentos.xlsx)
<img width="1302" height="455" alt="image" src="https://github.com/user-attachments/assets/e97bce7b-2c33-478a-ab1a-87b10b5740d7" />

### Agenda ou reagenda a visita na planilha
Cria uma linha na planilha Agenda.xlsx para a visita do cliente Rafael:
<img width="1276" height="131" alt="image" src="https://github.com/user-attachments/assets/5a72df3f-d22f-4066-8c45-f2f3e19732f4" />

### E-mail enviado para o cliente
<img width="702" height="340" alt="image" src="https://github.com/user-attachments/assets/a2247175-e196-47a8-a13a-3abda47d5fa2" />

---
# Como utilizar

1. Importe o arquivo `AgenteIAImobiliario.json` no n8n.
2. Configure sua conta do Gmail.
3. Crie uma API Key no Google AI Studio.
4. Configure a credencial do Chat Model.
5. Conecte as duas planilhas no tools da agente de IA
6. Atualize o domínio utilizado na verificação de e-mails internos, caso necessário.
7. Publique o workflow.

---
## Autor
Cristina Yuki Yokomizo

🤝 Contribuições são sempre bem-vindas!
