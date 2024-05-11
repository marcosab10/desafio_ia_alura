# Buscador de Documentos Markdown com Embeddings

Este programa em Python busca em um repositório GitHub por arquivos Markdown e usa embeddings para encontrar o arquivo mais relevante para uma determinada consulta.

## Funcionalidades:

- Extrai todos os arquivos Markdown de um repositório GitHub especificado.
- Extrai as duas primeiras linhas não vazias de cada arquivo Markdown como título.
- Gera embeddings para o conteúdo de cada arquivo Markdown usando o modelo embedding-001 do Google Generative AI.
- Permite ao usuário inserir uma consulta de texto.
- Gera um embedding para a consulta.
- Calcula o produto escalar entre o embedding da consulta e os embeddings de cada arquivo Markdown.
- Retorna a URL do arquivo Markdown com a maior pontuação de similaridade.

## Requisitos:

- Python 3.7 ou superior
- Bibliotecas Python:
  - requests
  - base64
  - pandas
  - numpy
  - google-generativeai
- Uma chave de API do Google Generative AI

## Como usar:

- Instale as bibliotecas Python necessárias.
- Configure sua chave de API do Google Generative AI usando genai.configure(api_key="SUA_CHAVE_API").
- Especifique o proprietário do repositório GitHub e o nome do repositório na chamada de função get_markdown_files().
- Execute o notebook Python.
- Insira sua consulta de texto quando solicitado.
- O programa imprimirá a URL do arquivo Markdown mais relevante para sua consulta.

# Exemplo de uso

```python
df_markdown = get_markdown_files("marcosab10", "ICMC-USP")

consulta = "Ganhar Dinheiro explicado por Kiyosaki"

url_encontrada = gera_e_buscar_consulta(consulta, df_markdown, model)
print(url_encontrada)

```

## Possíveis melhorias:

- Adicionar suporte para outras branches do GitHub.
- Implementar paginação para lidar com repositórios grandes com muitos arquivos Markdown.
- Permitir ao usuário especificar um modelo de embedding diferente.
- Adicionar uma interface de usuário para facilitar o uso.
- Possível expandir essa lógica para fazer buscas e análises dos códigos fontes do repositório,
  o que é muito interessante.
