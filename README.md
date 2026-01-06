🎤 Assistente de Voz Inteligente com Whisper + ChatGPT
https://img.shields.io/badge/Python-3.8%252B-blue
https://img.shields.io/badge/OpenAI-Whisper%252BChatGPT-green
https://img.shields.io/badge/License-MIT-yellow
https://img.shields.io/badge/Colab-Try%2520It!-orange

Um assistente de voz completo que combina reconhecimento de fala (Whisper) com inteligência artificial conversacional (ChatGPT) para criar diálogos naturais entre humanos e máquinas.


✨ Funcionalidades Principais
🎤 Reconhecimento de fala em tempo real com Whisper

💬 Respostas inteligentes e contextuais com ChatGPT

🔊 Síntese de voz para respostas audíveis

🌍 Suporte multilíngue (Português, Inglês, Espanhol, Francês, Alemão)

🖥️ Interface web interativa com Gradio

📁 Processamento de arquivos de áudio (WAV, MP3)

🔄 Histórico de conversa para contexto contínuo


🚀 Começando Rápido
Pré-requisitos
Python 3.8 ou superior

Chave de API da OpenAI

Microfone (para uso com áudio ao vivo)


Instalação em 3 passos
Clone o repositório
bash
git clone https://github.com/sarmento92/DIO.git
cd DIO


Instale as dependências
bash
pip install openai-whisper openai gtts pydub gradio


Configure sua chave da OpenAI
python
# Método 1: Variável de ambiente
export OPENAI_API_KEY="sua-chave-aqui"

# Método 2: No código (apenas para teste)
import os
os.environ["OPENAI_API_KEY"] = "sua-chave-aqui"


Execução
Opção A: No Google Colab (Recomendado para testes)
python
!pip install openai-whisper openai gtts pydub gradio -q
# Execute as células do notebook


Opção B: Interface Web Local
bash
python -c "import gradio as gr; from app import interface; interface.launch()"


Opção C: Via Linha de Comando
python
from assistant import process_audio
result = process_audio("seu_audio.wav")
print(result)


🛠️ Estrutura do Projeto
text
DIO/
├── Assistente_Voz_Whisper_ChatGPT.ipynb  # Notebook principal
├── Assistente_Voz_Whisper_ChatGPT (1).ipynb  # Versão alternativa
├── README.md                            # Esta documentação
├── requirements.txt                     # Dependências (opcional)
└── examples/                            # Exemplos de uso
    ├── audio_teste.wav                  # Áudio de exemplo
    └── conversa_sample.json             # Histórico de conversa


    
