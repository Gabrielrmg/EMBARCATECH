# 📖 Documentação do Projeto  

## ℹ️ Sobre este Repositório  

Este repositório contém a documentação do projeto, gerada com **MkDocs**. O site está disponível em:  

🔗 **[Acesse a documentação aqui](https://gabrielrmg.github.io/EMBARCATECH/)**  

## 🚀 Como Rodar o MkDocs Localmente  

Para visualizar a documentação localmente, siga os passos abaixo:  

### 1️⃣ **Clone o repositório**  

Antes de clonar, é necessário configurar **SSH** no seu ambiente.  

- **Gerar uma chave SSH**: [Instruções aqui](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)  
- **Adicionar a chave no GitHub**: [Instruções aqui](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)  

Após configurar o SSH, clone o repositório usando:  
```bash
git clone git@github.com:Gabrielrmg/EMBARCATECH.git
cd EMBARCATECH
```

### 2️⃣ **Instale as dependências**  

Se você ainda não tiver, instale o **Python** e o gerenciador de pacotes `pip`. Em seguida, instale os pacotes necessários com:  
```bash
pip install -r requirements.txt
```

### 3️⃣ **Inicie o servidor local**  

Execute o comando abaixo para rodar o MkDocs localmente:  
```bash
mkdocs serve
```
Isso iniciará um servidor local. Você pode acessar a documentação pelo navegador em:  
```
http://127.0.0.1:8000/
```

## 🔄 Atualização do Site  

A documentação é hospedada no **GitHub Pages** e gerada automaticamente pela branch `gh-deploy`. Caso precise atualizar o site manualmente, execute:  
```bash
mkdocs gh-deploy
```
Isso irá gerar os arquivos estáticos e publicá-los na branch [`gh-deploy`](https://github.com/Gabrielrmg/EMBARCATECH/tree/gh-pages?tab=readme-ov-file).