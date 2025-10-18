# SAR Autoencoders

Projeto de pesquisa para treinamento e avaliação de diferentes arquiteturas de autoencoders aplicados a imagens SAR (Search and Rescue).

## Visão Geral

Este projeto apresenta a implementação e comparação de modelos de autoencoders para compressão e reconstrução de imagens SAR. São explorados três tipos principais de autoencoders:

- Autoencoder Convencional (Convencional)
- Autoencoder Variacional (Variacional VAE)
- Autoencoder com Penalidade de Redundância (Redundância)

Cada modelo é treinado, avaliado com métricas quantitativas (PSNR, SSIM, MS-SSIM)  e otimizado usando tuning automático de hiperparâmetros com Keras/Optuna.

## Funcionalidades principais

- Pré-processamento dos dados de imagem (redimensionamento, normalização)
- Definição de vários modelos variantes de autoencoders
- Treinamento com callbacks para early stopping e scheduler de learning rate
- Avaliação detalhada dos modelos com várias métricas quantitativas
- Geração de gráficos de perda, comparativos e reconstruções visuais
- Otimização de hiperparâmetros usando Keras Tuner e Optuna
- Conversão dos modelos para formatos compatíveis com Edge Impulse e quantização INT8

## Requisitos

- Python 3.x
- TensorFlow 2.x
- Keras Tuner
- Optuna

## Estrutura de arquivos

- `SAR-AE.ipynb` - Notebook com todo o código, explicações e visualizações
- `models/` - Diretório onde os modelos treinados são salvos
- `plots/` - Gráficos gerados durante o treinamento e avaliação
- `results/` - Métricas e arquivos de log dos experimentos

## Como usar

1. Carregue os dados de imagens para a pasta a pasta dataset: https://www.kaggle.com/datasets/nikolasgegenava/sard-2-search-and-rescue-dataset-extra-classes
2. Execute as células para pré-processamento.
3. Configure e treine o modelo desejado (Convencional, Variacional, Redundância).
4. Avalie os resultados com as métricas implementadas.
5. Utilize os gráficos e logs para análise do desempenho.
6. Caso queira otimizar hiperparâmetros, execute a rotina de tuning.
7. Salve os melhores modelos para uso futuro.

## Métricas de avaliação

- **PSNR** (Peak Signal-to-Noise Ratio): indica a fidelidade da reconstrução pixel a pixel.
- **SSIM** (Structural Similarity Index): avalia luminescência, contraste e estrutura.
- **MS-SSIM** (Multi-Scale Structural Similarity): extensão do SSIM em múltiplas escalas.
- **Tempo de inferência:** desempenho e eficiência do modelo.

## Futuras melhorias

- Uso de funções de perda mais avançadas como SSIM-MSE combinada.
- Arquitetura de autoencoder assimétrico com maior capacidade de extração.
- Integração com frameworks específicos para deploy em dispositivos embutidos.
