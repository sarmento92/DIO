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
📖 Como Usar
1. Processamento de Arquivo de Áudio
python
from assistant import processar_audio

# Processa um arquivo de áudio
pergunta, resposta, audio = processar_audio("pergunta.wav")
print(f"Você disse: {pergunta}")
print(f"Assistente: {resposta}")
2. Interface Web Interativa
Execute o notebook e rode a célula da interface Gradio para uma interface visual onde você pode:

Fazer upload de arquivos de áudio

Escolher o idioma

Ouvir a resposta em voz

Ver a transcrição e resposta em texto

3. Personalização
python
# Escolha o modelo Whisper (tiny, base, small, medium, large)
modelo = whisper.load_model("small")

# Ajuste o ChatGPT
resposta = conversar_com_gpt(
    mensagem, 
    temperature=0.7,  # Controle de criatividade (0-1)
    max_tokens=300    # Tamanho da resposta
)
🔧 Configuração Avançada
Modelos Whisper Disponíveis
Modelo	Tamanho	Velocidade	Precisão	Uso Recomendado
tiny	39 MB	⚡ Muito rápido	⭐ Básico	Testes rápidos
base	74 MB	⚡⚡ Rápido	⭐⭐ Boa	Uso geral
small	244 MB	🐢 Normal	⭐⭐⭐ Muito boa	Produção
medium	769 MB	🐢🐢 Lento	⭐⭐⭐⭐ Excelente	Alta precisão
large	1550 MB	🐢🐢🐢 Muito lento	⭐⭐⭐⭐⭐ Superior	Pesquisa
Idiomas Suportados
Português (pt)

Inglês (en)

Espanhol (es)

Francês (fr)

Alemão (de)

Todos os idiomas do Whisper

🐛 Solução de Problemas
Problema	Causa	Solução
Erro 429 (Quota Exceeded)	Limite da API OpenAI	Verifique sua quota em platform.openai.com
Whisper não instala	Dependências conflitantes	Use pip install openai-whisper
Áudio não reproduz	Codecs ausentes	Instale ffmpeg: sudo apt install ffmpeg
API Key não reconhecida	Variável de ambiente mal configurada	Use print(os.getenv("OPENAI_API_KEY")) para verificar
📊 Exemplo de Uso Completo
python
# 1. Importar
import whisper
import openai
from gtts import gTTS

# 2. Configurar
openai.api_key = "sua-chave"
modelo = whisper.load_model("base")

# 3. Transcrever áudio
transcricao = modelo.transcribe("audio.wav", language="pt")

# 4. Obter resposta
resposta = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[{"role": "user", "content": transcricao["text"]}]
)

# 5. Converter para voz
tts = gTTS(text=resposta.choices[0].message.content, lang="pt")
tts.save("resposta.mp3")
🔮 Roadmap e Melhorias Futuras
Síntese de voz mais natural (ElevenLabs, Google TTS)

Integração com APIs externas (Google, Wikipedia, Clima)

Interface mobile (App Android/iOS)

Comandos de voz ("abra o navegador", "pesquise por...")

Aprendizado por contexto (memória de longo prazo)

Análise de sentimentos na voz

Modo offline com modelos locais

⚠️ Avisos Importantes
Segurança
NUNCA compartilhe sua API Key publicamente

A chave no código é apenas para demonstração

Use variáveis de ambiente ou sistemas de gestão de secrets

Custos
Whisper é gratuito para uso

ChatGPT tem custos por uso (confira os preços em openai.com/pricing)

Monitor seu uso regularmente para evitar surpresas

Limitações
Precisão do Whisper varia com qualidade do áudio

Latência pode ocorrer em conexões lentas

ChatGPT pode apresentar "alucinações" (respostas incorretas)

🤝 Contribuindo
Contribuições são bem-vindas! Siga estes passos:

Faça um Fork do projeto

Crie uma Branch para sua feature (git checkout -b feature/Incivel)

Commit suas mudanças (git commit -m 'Adiciona feature incível')

Push para a Branch (git push origin feature/Incivel)

Abra um Pull Request

📚 Aprenda Mais
Documentação Oficial do Whisper

Guia da OpenAI API

Tutorial de Gradio

Curso de Processamento de Áudio com Python

📄 Licença
Este projeto está licenciado sob a Licença MIT - veja o arquivo LICENSE para detalhes.

✍️ Autor
sarmento92 - GitHub
Projeto desenvolvido como parte da formação em IA da DIO (Digital Innovation One).

🌟 Agradecimentos
Equipe da OpenAI pelos modelos Whisper e ChatGPT

Comunidade Python pelas bibliotecas incríveis

Google Colab pelo ambiente gratuito de execução

DIO pela oportunidade de aprendizado

<div align="center">
⭐ Se este projeto foi útil, deixe uma estrela no repositório!
https://img.shields.io/github/stars/sarmento92/DIO?style=social

Perguntas? Abra uma issue no GitHub!

</div>
✨ Tecnologia que entende e responde como um humano.
