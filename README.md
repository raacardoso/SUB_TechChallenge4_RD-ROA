# SubTechChallenge4 — RD&ROA: Relatório de Detecção de Riscos, Objetos e Atividades  
# SubTechChallenge4 — RD&ROA: Risk, Object and Activity Detection Report  

---

## Descrição do Projeto | Project Description
O RD&ROA foi desenvolvido como parte do Tech Challenge 4 da pós-graduação em Inteligência Artificial da FIAP.  
Seu objetivo é demonstrar a aplicação prática de Visão Computacional e Inteligência Artificial em cenários reais, utilizando gravações de câmeras de segurança para detectar, rastrear e classificar objetos, pessoas e atividades, além de gerar relatórios automáticos com níveis de severidade de risco.

RD&ROA was developed as part of Tech Challenge 4 of the postgraduate program in Artificial Intelligence at FIAP.  
Its goal is to demonstrate the practical application of Computer Vision and Artificial Intelligence in real-world scenarios, using surveillance footage to detect, track, and classify objects, people, and activities, as well as to automatically generate reports with risk severity levels.

---

## Descrição Técnica | Technical Overview
A aplicação realiza uma análise automatizada de vídeo para identificar:
- Pessoas, carros, motos e animais em cena;  
- Ações humanas (andar, correr, parado, interagir);  
- Eventos anômalos e atividades de risco;  
- Geração de relatórios automáticos em `.docx` com miniaturas ilustrativas.

The application performs automated video analysis to identify:
- People, cars, motorcycles, and animals in the scene;  
- Human actions (walking, running, standing still, interacting);  
- Anomalous events and risky activities;  
- Automatic `.docx` report generation with summaries and thumbnails.

---

## Tecnologias Utilizadas | Technologies Used

- Linguagem / Language: Python 3.10  
- Modelos / Models:  
  - `yolov8m.pt` → Detecção e rastreamento de objetos / Object detection and tracking  
  - `yolov8n-pose.pt` → Detecção de pose e classificação de atividades humanas / Human pose detection and activity classification  
- Bibliotecas Principais / Main Libraries:  
  - `opencv-python` — Leitura e processamento de vídeo / Video processing  
  - `ultralytics` — Execução dos modelos YOLOv8 / YOLOv8 framework  
  - `numpy` — Cálculos matemáticos e estatísticos / Numerical computation  
  - `python-docx` — Criação automática do relatório / Automated reporting  
  - `collections` — Estruturação de dados e rastreamento de IDs / Data structuring and ID tracking  

---

## Estrutura do Projeto | Project Structure

- Detecção e Rastreamento / Detection & Tracking:  
  O modelo `yolov8m.pt` identifica pessoas, veículos e animais, atribuindo IDs únicos e salvando miniaturas representativas.  
  The `yolov8m.pt` model identifies people, vehicles, and animals, assigning unique IDs and saving representative thumbnails.  

- Classificação de Atividades / Activity Classification:  
  O modelo `yolov8n-pose.pt` analisa 17 pontos corporais e classifica o comportamento humano em:  
  The `yolov8n-pose.pt` model analyzes 17 body keypoints and classifies human behavior as:  
  - Parado / Standing  
  - Andando / Walking  
  - Correndo / Running  
  - Interagindo / Interacting  

- Classificação de Severidade (ARCS) / Severity Classification (ARCS):  
  Cada evento é categorizado de acordo com o nível de risco:  
  Each event is categorized by its risk level:  
  - Leve / Low  
  - Aceitável / Acceptable  
  - Potencial Risco / Potential Risk  

- Relatório Automático / Automated Report:  
  Gera um documento `.docx` com:  
  Generates a `.docx` report containing:  
  - Seção de detecção de objetos (com IDs e imagens) / Object detection section (with IDs and images)  
  - Atividades humanas detectadas / Human activity summary  
  - Classificação de riscos por severidade / Risk classification by severity  
  - Total de ocorrências e estatísticas gerais / Total occurrences and statistics  

---

## Próximas Atualizações | Upcoming Updates

### Atualização do Modelo — YOLOv8x-Pose / Model Upgrade — YOLOv8x-Pose
A próxima versão substituirá `yolov8n-pose.pt` por `YOLOv8x-pose.pt`, o modelo mais robusto da família Ultralytics, com maior precisão na detecção de keypoints.  
The next version will replace `yolov8n-pose.pt` with `YOLOv8x-pose.pt`, the most robust Ultralytics model, offering higher accuracy for keypoint detection.

Motivos / Reasons:  
- Melhor identificação de atividades humanas complexas / Improved recognition of complex human activities (sitting, bending, gesturing).  
- Maior precisão em ambientes com oclusão ou multidão / Better performance in crowded or partially occluded environments.  
- Menos falsos positivos em movimentos sutis / Fewer false positives in subtle movements.  

---

### Classificação de Ações Contextuais / Contextual Action Classification
Integração de redes temporais para identificar ações compostas, como:  
Integration of temporal classification networks to recognize complex actions such as:  
- Pessoa atravessando fora da faixa / Person crossing outside a crosswalk  
- Motocicleta na calçada / Motorcycle on the sidewalk  
- Animal correndo na via / Animal running on the street  

Essas análises, combinadas com o histórico e contexto espacial, melhorarão a interpretação semântica dos comportamentos.  
These analyses, combined with temporal and spatial context, will enhance semantic interpretation of behaviors.

---

### Heatmap e Fluxo de Movimento / Heatmap and Movement Flow
Será adicionada uma camada de visualização com:  
A new visualization layer will include:  
- Heatmaps para mostrar o fluxo comum / to display common movement flow  
- Zonas de interesse (.YAML) configuráveis / Configurable zones of interest (.YAML)  
- Direcionalidade e velocidade média por zona / Directional tracking and average speed per zone  

---

## Créditos | Credits
Autor / Author: Ramon C. Sancha  
RM: 356432  
Instituição / Institution: FIAP — Pós-Graduação em Inteligência Artificial / FIAP — Postgraduate Program in Artificial Intelligence  
Desafio / Challenge: Tech Challenge Fase 4 — Visão Computacional Aplicada / Tech Challenge Phase 4 — Applied Computer Vision  
Projeto / Project: RD&ROA — Risk, Object, and Activity Detection Report  
