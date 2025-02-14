# 📰 Coletor de Feeds RSS - Google News

Este projeto realiza a coleta automatizada de notícias do **Google News** via **RSS Feed**, extraindo **títulos, links, descrições e datas de publicação** para palavras-chave específicas.

## 📌 Funcionalidades

✅ Pesquisa de notícias no **Google News** usando palavras-chave  
✅ Extração de **título, link, descrição e data de publicação**  
✅ Conversão das datas para formato legível  
✅ Organização dos dados em um **dataframe R**  
✅ Facilidade para modificar palavras-chave de pesquisa  

---

## 🛠 Tecnologias Utilizadas

- **Linguagem:** R  
- **Pacotes:** `xml2`, `httr`, `dplyr`, `parsedate`  
- **Fonte de dados:** **Google News RSS Feeds**  

---

## 📂 Estrutura do Código

```
📁 /  (Diretório Raiz)
├── 00_feed_RSS.R   # Script principal de coleta de feeds RSS
└── feeds_coletados.csv   # Arquivo de saída (caso seja salvo)
```

---

## 🚀 Como Executar

### 1️⃣ **Instalar os pacotes necessários**

Se ainda não estiverem instalados, execute no R:

```r
install.packages(c("xml2", "dplyr", "httr", "parsedate"))
```

### 2️⃣ **Modificar palavras-chave de pesquisa**

No script `00_feed_RSS.R`, edite a variável `queries` para incluir os termos desejados:

```r
queries <- c("lgpd", "anpd", "inteligência artificial")
```

### 3️⃣ **Executar o Script**

Rode o script `00_feed_RSS.R` no **RStudio** ou diretamente no R:

```r
source("00_feed_RSS.R")
```

Os resultados serão exibidos como um **dataframe** no console.

---

## 📊 Estrutura do DataFrame

A saída será um dataframe com as seguintes colunas:

| Título | Link | Descrição | Data Publicação | Data Formatada | Palavra-chave |
|--------|------|-----------|----------------|----------------|---------------|
| Título da Notícia | URL da Notícia | Resumo da Notícia | Data no formato original | Data em `dd/mm/yyyy` | Palavra-chave usada na busca |

---

## 🛑 Possíveis Problemas e Soluções

### ⚠️ **Erro ao acessar o Feed RSS**
Se o Google bloquear a requisição, tente alterar o **User-Agent** no código:

```r
response <- GET(url, add_headers('User-Agent' = 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) Chrome/91.0.4472.124 Safari/537.36'))
```

### ⏳ **A coleta parece lenta?**
Se houver **muitas palavras-chave**, experimente adicionar um pequeno **delay** entre as requisições:

```r
Sys.sleep(2)  # Espera 2 segundos entre cada requisição
```

---

## 👨‍💻 Autor

👤 **José Tenório Abs Junior**  
📧 [Seu Email]  
🏛 **IBPAD - Instituto Brasileiro de Pesquisa e Análise de Dados**  

🚀 **Agora você pode coletar notícias automaticamente!** Qualquer dúvida, me avise! 😊
