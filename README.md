
# 🚗 Projeto: Catálogo Digital - Johnny Motors

![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-yellow)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-1.30%2B-red)

## 📖 Situação de Aprendizagem

### Contexto
Você e sua equipe foram contratados pela **Johnny Motors**, uma concessionária de veículos clássicos e esportivos que está expandindo sua atuação para o ambiente digital.

Atualmente, a empresa possui um banco de dados com milhares de informações técnicas sobre os veículos (marca, modelo, ano, motor, potência, etc.) e uma vasta galeria de imagens hospedadas em um CDN externo. No entanto, a experiência do cliente ainda é muito técnica e pouco visual.

### O Desafio
O proprietário da **Johnny Motors**, o Sr. Johnny, solicitou o desenvolvimento de um **Catálogo Digital Interativo** que permita aos clientes:
1.  Navegar facilmente entre as marcas e modelos disponíveis.
2.  Visualizar fotos de alta qualidade de cada veículo.
3.  Consultar as especificações técnicas de forma clara e amigável.

Sua missão é transformar os dados brutos em uma aplicação web funcional, intuitiva e visualmente atraente utilizando **Python** e **Streamlit**.

---

## 🎯 Objetivos de Aprendizagem

Ao final deste projeto, os alunos serão capazes de:
-   Manipular e limpar dados tabulares com a biblioteca **Pandas**.
-   Desenvolver interfaces web interativas com **Streamlit**.
-   Implementar lógica de **filtros em cascata** (Seleção de Marca -> Modelo).
-   Gerenciar o estado da aplicação utilizando `st.session_state` (para navegação de fotos).
-   Consumir e exibir imagens externas via URL.
-   Criar uma galeria de miniaturas (thumbnails) interativa.

---

## 🛠️ Tecnologias Utilizadas

-   **Python 3.10+**: Linguagem base do projeto.
-   **Pandas**: Para leitura, limpeza e manipulação do dataset `data_full.csv`.
-   **Streamlit**: Framework para criação da interface web.
-   **Pillow (PIL)**: (Opcional) Para manipulação de imagens, caso necessário.

---

## 📂 Estrutura do Repositório

```
johnny-motors-catalog/
│
├── data/
│   └── data_full.csv          # Dataset com informações dos carros (Kaggle)
│
├── app.py                     # Código principal da aplicação Streamlit
├── requirements.txt           # Dependências do projeto
└── README.md                  # Este arquivo
```

---

## 🚀 Como Executar o Projeto

### 1. Pré-requisitos
Certifique-se de ter o Python instalado em sua máquina.

### 2. Clone o repositório
```bash
git clone https://github.com/seu-usuario/johnny-motors-catalog.git
cd johnny-motors-catalog
```

### 3. Crie um ambiente virtual (Recomendado)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python3 -m venv venv
source venv/bin/activate
```

### 4. Instale as dependências
```bash
pip install -r requirements.txt
```

### 5. Execute a aplicação
```bash
streamlit run app.py
```
A aplicação abrirá automaticamente no seu navegador padrão (geralmente em `http://localhost:8501`).

---

## 🧠 Desafios e Requisitos Técnicos

Para que o projeto atenda às expectativas do Sr. Johnny, a aplicação deve conter:

### 1. Filtros Inteligentes (Cascata)
-   [ ] O usuário deve poder selecionar uma **Marca**.
-   [ ] Após selecionar a marca, o seletor de **Modelos** deve ser atualizado automaticamente, mostrando apenas os modelos daquela marca.

### 2. Galeria de Fotos Interativa
-   [ ] O sistema deve ler a coluna `image_urls` (que contém links separados por vírgula).
-   [ ] A imagem principal deve ser exibida em destaque.
-   [ ] Botões de **"Anterior"** e **"Próxima"** devem permitir a navegação.
-   [ ] Uma **galeria de miniaturas** deve ser exibida abaixo, permitindo clicar em qualquer foto para vê-la em tamanho grande.
-   [ ] O índice da foto deve resetar ao trocar de carro.

### 3. Painel de Informações
-   [ ] Abaixo das fotos, exibir um painel formatado (Markdown) com:
    -   Ano de fabricação (`from_year` - `to_year`)
    -   Especificações Técnicas (Motor, Potência, Torque, Transmissão, etc.)
    -   Descrição do veículo.

---

## 💡 Dicas e Observações para os Alunos

1.  **Tratamento de Dados Nulos**: O dataset original possui muitos valores nulos (NaN). Use `.dropna()` ou `.get('coluna', 'N/A')` para evitar erros na interface.
2.  **Performance**: Utilize o decorador `@st.cache_data` na função de leitura do CSV. Isso evita que o arquivo seja lido novamente a cada clique do usuário.
3.  **Session State**: O Streamlit recarrega o script a cada interação. Para manter o controle de qual foto está sendo exibida, use `st.session_state`.
4.  **Strings para Listas**: A coluna `image_urls` vem como uma única string. Use o método `.split(',')` para transformá-la em uma lista de links.
5.  **Caminhos de Imagem**: Como as imagens são URLs externas, não é necessário baixá-las. O `st.image()` aceita URLs diretamente.

---

## 📊 Fonte dos Dados

Os dados utilizados neste projeto foram obtidos no [Kaggle - Cars Dataset](https://www.kaggle.com/). O arquivo `data_full.csv` contém informações detalhadas sobre veículos de diversas marcas e anos.

---

## 🤝 Contribuições

Este projeto é de cunho educacional. Sinta-se à vontade para propor melhorias, corrigir bugs ou adicionar novas funcionalidades (como filtros por ano ou potência).

---

**Desenvolvido com 💙 para a Johnny Motors.**
*"Se não tem na Johnny Motors, você não precisa."*
