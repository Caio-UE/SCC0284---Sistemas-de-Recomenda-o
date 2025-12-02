# Privacidade Diferencial em Sistemas de Recomendação

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/16QvUiAyU7zKV87pOzdR653DRgSTZusdr#scrollTo=XgAnNqNdo8kT)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Status](https://img.shields.io/badge/Status-Concluído-green)

---

## O Objetivo
Sistemas de recomendação (como Netflix e Spotify) precisam de dados dos usuários para funcionar. Porém, como garantir que o histórico de um usuário não seja exposto ao calcularmos estatísticas globais?

Este projeto visa ensinar, de forma prática e interativa, o conceito de **Privacidade Diferencial (Differential Privacy)**, demonstrando como adicionar ruído matemático calibrado para proteger dados individuais sem destruir a utilidade das informações gerais.

## Material Didático Produzido

O projeto é composto por três partes integradas:

1.  __Tutorial Interativo (Jupyter Notebook):__ O arquivo `Privacidade_Diferencial.ipynb` contém todo o código explicado passo-a-passo.
2.  __Videoaula:__ Uma explicação visual dos conceitos e demonstração do código. [Clique aqui para assistir](https://youtu.be/0KcLEsLCch4?si=cX6y5cD9lDnRNaAC).
3.  __Código Fonte:__ Implementação utilizando a biblioteca `diffprivlib` da IBM.

## O Cenário de Teste ("Toy Story")

Para não expor dados reais, simulamos um banco de dados com **5.000 avaliações** de usuários para o filme *Toy Story* (notas de 1 a 5).

O desafio proposto no código é:
1.  Calcular a nota média do filme (Ground Truth).
2.  Aplicar o **Mecanismo de Laplace** para proteger a média.
3.  Comparar a precisão do resultado variando o parâmetro **Épsilon ($\epsilon$)** e visualizar o *trade-off* entre privacidade e utilidade.

### Principais Resultados Observados
Com uma base de dados robusta (5.000 amostras), observamos que:
* **$\epsilon$ Baixo (0.01):** Privacidade máxima. Devido ao volume de dados, a perda de precisão foi aceitável (média variando entre 3.9 e 4.1).
* **$\epsilon$ Moderado (0.1 - 0.5):** O ponto ideal (*Sweet Spot*). O ruído protege os dados individuais, mas a média final é praticamente idêntica à real.
* **$\epsilon$ Alto (10.0):** Baixa privacidade, resultado sem distorção.

## Como Rodar este Projeto

### Opção 1: Google Colab (Recomendado)
A maneira mais fácil é clicar no badge "Open in Colab" no topo deste arquivo. O notebook abrirá diretamente no seu navegador, pronto para execução, sem necessidade de instalações locais.

### Opção 2: Execução Local
Se preferir rodar na sua máquina, você precisará instalar as dependências listadas abaixo:

```bash
pip install diffprivlib pandas matplotlib seaborn notebook
