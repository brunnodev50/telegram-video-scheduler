# 📹 Telegram Video Scheduler

Aplicativo desktop em Python (Tkinter) para agendar e enviar vídeos automaticamente em um grupo do Telegram com legendas, intervalo configurável entre envios e reset automático do ciclo a cada 12 horas.

---

## 📋 Requisitos

- Python 3.8+
- Biblioteca Telethon
- Conta do Telegram com permissão de admin no grupo

---

## ⚙️ Instalação

1. **Clone o repositório**
```bash
   git clone https://github.com/brunnodev50/telegram-video-scheduler.git
   cd telegram-video-scheduler
```

2. **Instale as dependências**
```bash
   pip install telethon
```

---

## 🔑 Configuração

1. Acesse [https://my.telegram.org](https://my.telegram.org)
2. Faça login com sua conta do Telegram
3. Clique em **API development tools**
4. Crie um novo app e copie seu `api_id` e `api_hash`

5. Abra o arquivo `bot_videos.py` e preencha as credenciais:
```python
   API_ID = 0            # seu api_id (número)
   API_HASH = ""         # seu api_hash
   PHONE = ""            # seu número com DDI, ex: +5511999999999
   GROUP = ""            # link do grupo, ex: "https://t.me/+XXXXXX"
```

---

## ▶️ Como usar
```bash
python bot_videos.py
```

1. Clique em **📁** para selecionar um vídeo do seu computador
2. Escreva a legenda do vídeo
3. Clique em **＋ ADICIONAR**
4. Repita para os demais vídeos (máximo 30)
5. Configure o **intervalo entre vídeos** (padrão: 15 minutos)
6. Clique em **💾 SALVAR**
7. Clique em **▶ INICIAR**

---

## 🔄 Como funciona

- Os vídeos são enviados um a um no intervalo configurado
- Após todos os vídeos serem enviados, o bot aguarda completar **12 horas**
- Ao completar 12 horas, todas as mensagens enviadas são **apagadas automaticamente**
- O ciclo **reinicia do zero** automaticamente
- Ao clicar em **↺ RESETAR CICLO**, o histórico de envios é limpo e o ciclo recomeça mantendo os vídeos cadastrados

---

## 🖥️ Interface

| Elemento | Função |
|---------|--------|
| Lista de vídeos | Exibe todos os vídeos cadastrados |
| 📁 Botão | Abre o explorador de arquivos para selecionar vídeo |
| Legenda | Texto que acompanha cada vídeo |
| ＋ Adicionar | Adiciona vídeo à lista |
| ✎ Atualizar | Atualiza o vídeo selecionado |
| ✕ Remover | Remove o vídeo selecionado |
| 💾 Salvar | Salva todas as configurações |
| ▶ Iniciar | Inicia o envio agendado |
| ■ Parar | Para o bot |
| ↺ Resetar Ciclo | Limpa histórico e reinicia do vídeo 1 |
| Log | Exibe em tempo real o status dos envios |

---

## 📁 Estrutura do projeto
```
telegram-video-scheduler/
├── bot_videos.py       # script principal
├── videos_db.json      # banco de dados local (gerado automaticamente)
└── README.md           # este arquivo
```

---

## 🔒 Segurança

- **Nunca compartilhe** seu `API_ID`, `API_HASH` ou número de telefone publicamente
- **Nunca suba** o `bot_videos.py` preenchido ou o arquivo `session.session` para o GitHub
- O `.gitignore` já está configurado para proteger esses arquivos

---

## ⚠️ Observações importantes

- Você precisa ser **admin** do grupo com permissão de enviar e apagar mensagens
- Os vídeos são enviados a partir do **seu perfil pessoal** do Telegram
- O banco de dados `videos_db.json` é salvo localmente e sobrevive a reinicializações
- Respeite os **Termos de Serviço** do Telegram — não utilize para spam ou abuso
