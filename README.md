## 🔧 Configuração

1. **Crie uma conta OpenAI** (grátis com $5 crédito)
   - Acesse: [platform.openai.com](https://platform.openai.com)
   
2. **Gere sua API Key:**
   - Vá em "API Keys" → "Create new secret key"
   - **Copie** a chave (aparece só uma vez!)

3. **No Google Colab:**
   - Painel esquerdo → ícone de cadeado 🔒
   - "+ Novo segredo"
   - Nome: `OPENAI_API_KEY`
   - Valor: `sua-chave-aqui`

4. **Execute as células** em ordem

⚠️ **NUNCA** compartilhe sua API Key publicamente!








# Assistente de Voz Inteligente com Whisper + ChatGPT

Um assistente de voz completo que combina reconhecimento de fala (Whisper) com inteligência artificial conversacional (ChatGPT) para criar diálogos naturais entre humanos e máquinas.

## 🚀 Comece Rápido

### Pré-requisitos
- Python 3.8 ou superior
- Chave de API da OpenAI
- Microfone (opcional, para uso ao vivo)

### Instalação

1. **Clone o repositório**
```bash
git clone https://github.com/sarmento92/DIO.git
cd DIO

Instale as dependências
pip install openai-whisper openai gtts pydub gradio

Configure sua chave da OpenAI
export OPENAI_API_KEY="sua-chave-aqui"

Como Usar
Execute o notebook principal:
jupyter notebook Assistente_Voz_Whisper_ChatGPT.ipynb

🎯 Funcionalidades
🎤 Reconhecimento de fala com Whisper da OpenAI

💬 Respostas inteligentes com ChatGPT

🔊 Síntese de voz usando gTTS (Google Text-to-Speech)

🌍 Multilíngue suporta vários idiomas

🖥️ Interface web com Gradio

📁 Processa arquivos de áudio (WAV, MP3)


