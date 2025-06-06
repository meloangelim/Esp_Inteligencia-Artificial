
# 📄 Extração e Cruzamento de Dados para a empresa PyTravel com o intuito de melhorar as viagens dos Usuários.

Este projeto tem como objetivo extrair e organizar informações do arquivo `Catálogo de Destinos - PyTravel  .docx` com destinos turísticos categorizados por tipo de cidade e meio de transporte, utilizando a biblioteca `python-docx`. Ao final, ele cruza essas informações para gerar insights sobre quais destinos compartilham múltiplas características.


## 🧰 Requisitos

Antes de executar o script, certifique-se de instalar a biblioteca necessária:

```bash
pip install python-docx
```


## 📁 Estrutura do Arquivo `Catálogo de Destinos - PyTravel  .docx`

O script espera que o documento Word (`Catálogo de Destinos - PyTravel  .docx`) contenha seções identificadas por títulos com os seguintes padrões:

- **Destinos para Cidades Praianas**
- **Destinos para Cidades Capitais**
- **Destinos para Cidades Interiorana**
- **Pacotes de Avião**
- **Pacotes de Ônibus**
- **Pacotes de Navio**

Cada seção deve ser seguida por uma lista de cidades, uma por linha.


## 📜 Descrição do Código

### 1. `extrair_secoes(arquivo)`

- **Entrada:** Caminho para o arquivo `Catálogo de Destinos - PyTravel  .docx`.
- **Processo:** Percorre os parágrafos do documento e organiza as cidades encontradas em um dicionário conforme suas seções.
- **Saída:** Um dicionário com listas de cidades por categoria:

```python
{
    "praias": [...],
    "capitais": [...],
    "interior": [...],
    "avioes": [...],
    "onibus": [...],
    "navio": [...]
}
```

### 2. `exibir_lista(titulo, lista)`

- Exibe no console os itens de uma lista, precedidos por seu título e a quantidade de elementos.

### 3. `cruzamento(nome, lista1, lista2)`

- Realiza a interseção entre duas listas, retornando os itens comuns a ambas.



## 📌 Exemplo de Uso

### 1. Leitura do documento e extração das seções:

```python
arquivo = "Catálogo de Destinos - PyTravel .docx"
secoes = extrair_secoes(arquivo)
```

### 2. Exibição das listas extraídas:

```python
exibir_lista("Destinos praianos", secoes["praias"])
# ... idem para outras categorias
```

### 3. Cruzamento de dados:

```python
capitais_praianas = cruzamento("Capitais praianas", secoes["capitais"], secoes["praias"])
```

### 4. Exibição dos cruzamentos:

```python
exibir_lista("Capitais que são cidades praianas", capitais_praianas)
```


## ✅ Exemplos de Cruzamentos Realizados

- **Capitais que também são cidades praianas**
- **Destinos de praias com pacotes de ônibus**
- **Cidades do interior com pacotes de avião**
- **Capitais com rotas de navio**

Esses cruzamentos ajudam a identificar destinos turísticos versáteis e bem conectados.


## 🚀 Possíveis Melhorias

- Exportar os resultados para arquivos `.csv` ou `.xlsx`
- Suportar diferentes estruturas de documento
- Interface gráfica com filtros dinâmicos
- Validação e normalização de nomes de cidades


## 📄 Licença

Este projeto é livre para uso educacional e não possui fins comerciais.
