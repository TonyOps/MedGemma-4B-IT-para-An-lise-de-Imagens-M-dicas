# Utilizando LM Studio com Gemma 3 para Análise de Imagens Médicas

## 📌 Introdução
Este projeto demonstra a integração do **LM Studio** com o modelo **MedGemma-4B-IT**, uma variante especializada do **Gemma 3** desenvolvida para compreensão avançada de textos e imagens médicas. O MedGemma combina a arquitetura *decoder-only transformer* do Gemma 3 com treinamento específico em dados médicos, permitindo análise multimodal (texto + imagens) para aplicações clínicas.

A combinação do **LM Studio** (aplicação de desktop para execução local de modelos de IA) com o **MedGemma** cria um ambiente poderoso para interpretar imagens médicas complexas, como o caso de **linfoma periampular** disponível no [Radiopaedia](https://radiopaedia.org/cases/periampullary-lymphoma?lang=us).

---

## ⚙️ Pré-requisitos
- **LM Studio** (versão executável gratuita) - [Baixe aqui](https://lmstudio.ai/)
- Sistema operacional compatível: 
  - macOS (M1/M2/M3/M4)
  - Windows (x86 ou ARM)
  - Linux (x86 com suporte AVX2)
- Espaço em disco para armazenar modelos (varia conforme o modelo selecionado)

---

## 📥 Download e Configuração do LM Studio
### Passo a Passo:
1. **Baixe e instale o LM Studio**
   - Acesse [https://lmstudio.ai/](https://lmstudio.ai/) 
   - Clique no botão "Download" para obter a versão executável compatível com seu sistema
   - Instale a aplicação seguindo as instruções do instalador

2. **Abra o LM Studio**
   - Após a instalação, execute o aplicativo LM Studio (é uma aplicação desktop independente)
   - Você verá uma interface amigável com opções para buscar e baixar modelos

![Interface do LM Studio]  <img src="https://github.com/TonyOps/MedGemma-4B-IT-para-An-lise-de-Imagens-M-dicas/blob/main/Screenshot%202025-08-01%20151208.png?raw=true">
*Descrição: Tela inicial do LM Studio mostrando a busca de modelos.*

3. **Encontre e baixe o modelo Gemma 3**
   - Na aba "Search" do LM Studio, pesquise por "gemma"
   - Selecione o modelo **google/gemma-7b-it** ou **google/gemma-2b-it** (dependendo da capacidade do seu hardware)
   - Clique em "Download" para obter o modelo no formato GGUF (compatível com llama.cpp)

> **Nota**: O LM Studio não coleta seus dados ou monitora suas ações - todos os processos ocorrem localmente no seu computador, garantindo privacidade total. 

---

## 🖥️ Configuração do Modelo Gemma 3
### Passo a Passo:
1. **Localize o modelo baixado**
   - Após o download, vá para a aba "Local Server"
   - Clique em "Start Server" para ativar o servidor local

2. **Carregue o modelo Gemma 3**
   - Na aba "Chat", clique em "Select Model"
   - Escolha o modelo Gemma 3 que você baixou
   - Ajuste os parâmetros conforme necessário (temperatura, max tokens, etc.)

3. **Use o modelo para análise**
   - Para análise multimodal (imagens + texto), você precisará de um modelo específico como o MedGemma
   - Infelizmente, o LM Studio atualmente **não suporta modelos de geração de imagem**, mas você pode usar modelos de texto para interpretar descrições de imagens médicas 

![Busca de modelos no LM Studio] <img src="https://github.com/TonyOps/MedGemma-4B-IT-para-An-lise-de-Imagens-M-dicas/blob/main/Screenshot%202025-08-01%20151138.png?raw=true"> 
*Descrição: Busca pelo modelo Gemma no catálogo do LM Studio.*

---

## 🔍 Exemplo Prático: Linfoma Periampular
### Fluxo de Análise:
1. **Imagem de entrada**  
   Utilizamos o caso clínico do [Radiopaedia](https://radiopaedia.org/cases/periampullary-lymphoma?lang=us), que mostra achados de imagem relacionados a linfoma periampular. 

2. **Processamento pelo Gemma 3**
   - Descreva a imagem para o modelo em formato de texto
   - Faça perguntas específicas sobre os achados clínicos
   - O modelo gerará respostas baseadas em seu treinamento médico

### Exemplo de Prompt:
```
Analisar a seguinte descrição de imagem médica de um caso de linfoma periampular:
"Tomografia computadorizada demonstra massa heterogênea na região periampular com realce irregular após contraste. A lesão mede aproximadamente 3,5 cm e apresenta invasão da parede duodenal."

O que você pode concluir sobre este caso? Quais são os diagnósticos diferenciais mais prováveis?
```

### Resultado da Análise:
**Periampullary lymphoma**  

**Achados de imagem (TC):**  
- Massa grande, heterogeneamente realçada, parcialmente exofítica envolvendo a segunda e terceira partes do duodeno, envolvendo toda a circunferência, medindo cerca de 7 centímetros
- Dilatação aneurismática da segunda parte do duodeno
- Obstrução do ducto biliar comum com dilatação da árvore biliar a montante
- Massa parcialmente envolvendo a veia mesentérica superior
- Múltiplos linfonodos aumentados nas regiões paraaórtica, retrocaval e mesentérica
- Lesão hipoatenuante pequena vista no baço na fase venosa portal, sugestiva de envolvimento esplênico
- Esplenúla pequena observada
<br>
![Exemplo de análise no LM Studio]
<img src="https://github.com/TonyOps/MedGemma-4B-IT-para-An-lise-de-Imagens-M-dicas/blob/main/2df51fcb03da45f716ed77322b3fe9475f5559af23a197da66733b37ca799328.jpg?raw=true">  
*Descrição: Resultado da análise do caso de linfoma periampular no LM Studio com o modelo Gemma 3.*

---

## 📄 Licença
- LM Studio: Gratuito para uso pessoal e profissional ([termos](https://lmstudio.ai/))
- Modelos Gemma: Licença do Google Gemma (compatível com uso comercial com restrições específicas)

---

> **Nota do Autor**:  
> Este README foi estruturado para guiar usuários na integração prática do Gemma 3 com o LM Studio. O LM Studio é uma ferramenta excepcionalmente acessível para executar modelos de IA localmente, sem necessidade de conhecimentos técnicos avançados. Sua interface intuitiva permite que profissionais médicos explorem o potencial da IA sem depender de infraestrutura em nuvem ou preocupações com privacidade de dados.
> 
