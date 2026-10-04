# Ryo Yamada Beta Test — Cloudflare Pages

Site estático do **Ryo Yamada Beta Test**, preparado para ser hospedado no **Cloudflare Pages** através de um repositório do **GitHub**.

## Estrutura

```text
ryo-yamada-beta/
├── index.html
├── atualizacoes.html
└── README.md
```

Não é necessário Python, Node.js, banco de dados ou qualquer comando de build.

---

# 1. Criar o repositório no GitHub

1. Entre no GitHub:
   https://github.com/

2. Faça login na sua conta.

3. Clique em **New** para criar um novo repositório.

4. Escolha um nome, por exemplo:

```text
ryo-yamada-beta
```

5. Você pode deixar o repositório como **Public** ou **Private**.

6. Não é necessário criar README, `.gitignore` ou licença pelo GitHub, pois este projeto já possui os arquivos necessários.

7. Clique em **Create repository**.

---

# 2. Enviar os arquivos para o GitHub

Depois de criar o repositório:

1. Abra o repositório.
2. Clique em **Add file**.
3. Clique em **Upload files**.
4. Envie:

```text
index.html
atualizacoes.html
README.md
```

5. Clique em **Commit changes**.

A estrutura final deve ficar assim:

```text
ryo-yamada-beta
│
├── index.html
├── atualizacoes.html
└── README.md
```

O `index.html` precisa ficar na raiz do repositório.

---

# 3. Criar o projeto no Cloudflare Pages

1. Entre no painel da Cloudflare:
   https://dash.cloudflare.com/

2. Selecione sua conta.

3. Procure por **Workers & Pages**.

4. Escolha a opção para criar um novo projeto/site.

5. Selecione a opção de conectar com **GitHub**.

6. Autorize o Cloudflare a acessar o GitHub, caso seja solicitado.

7. Selecione o repositório:

```text
ryo-yamada-beta
```

---

# 4. Configurar o deploy

Como o projeto é um site HTML estático, use:

```text
Framework preset:
None

Build command:
deixar vazio

Build output directory:
/

Root directory:
/
```

Se o Cloudflare pedir um diretório de saída diferente, use a pasta onde o `index.html` está localizado.

Não instale dependências e não coloque comandos de build.

Depois clique em **Deploy**.

---

# 5. Seu site

Depois do primeiro deploy, o Cloudflare fornecerá um endereço parecido com:

```text
https://ryo-yamada-beta.pages.dev
```

Esse endereço pode ser usado imediatamente.

Posteriormente, você também pode conectar um domínio próprio pelo Cloudflare.

---

# 6. Como atualizar o site

A grande vantagem dessa configuração é que o Cloudflare pode publicar automaticamente cada alteração feita no GitHub.

Por exemplo, para adicionar uma atualização:

1. Abra o GitHub.
2. Entre no repositório.
3. Abra:

```text
atualizacoes.html
```

4. Clique para editar o arquivo.

5. Adicione uma nova atualização.

Exemplo:

```html
<article class="update">

    <div class="update-header">

        <h2>
            Nova atualização
        </h2>

        <span class="date">
            10/10/2026
        </span>

    </div>

    <span class="tag">
        UPDATE
    </span>

    <p>
        Descrição da atualização.
    </p>

</article>
```

6. Salve/commit a alteração.

O processo será:

```text
Você altera no GitHub
        ↓
GitHub recebe o commit
        ↓
Cloudflare detecta a alteração
        ↓
Cloudflare faz o deploy
        ↓
Site atualizado
```

Você não precisa desligar o site.

---

# 7. Alterar a página principal

Para alterar a página inicial:

```text
index.html
```

Faça a alteração no GitHub e faça o commit.

O Cloudflare fará um novo deploy automaticamente.

---

# 8. Como adicionar novas atualizações

No arquivo:

```text
atualizacoes.html
```

procure pelos blocos:

```html
<article class="update">
```

Você pode copiar um bloco existente e alterar:

- título
- data
- categoria
- descrição

Exemplo:

```html
<article class="update">

    <div class="update-header">

        <h2>
            Beta 0.2.0
        </h2>

        <span class="date">
            20/10/2026
        </span>

    </div>

    <span class="tag">
        BETA
    </span>

    <p>
        Uma nova versão do Beta Test foi disponibilizada
        com novos sistemas e correções.
    </p>

</article>
```

---

# 9. Atualizações sem derrubar o site

O Cloudflare Pages mantém o site funcionando enquanto uma nova versão é preparada.

Na prática:

```text
Versão atual
     ↓
Nova alteração no GitHub
     ↓
Novo deploy
     ↓
Nova versão publicada
```

Você não precisa parar o servidor porque não existe um servidor seu rodando esse site.

---

# 10. Recomendações

Mantenha sempre:

```text
index.html
atualizacoes.html
```

na raiz do projeto.

Não renomeie `index.html`, pois ele é a página inicial.

Também não coloque os arquivos dentro de uma pasta como:

```text
/site/index.html
```

a menos que você configure o diretório raiz do Cloudflare para essa pasta.

---

## Resumo

### GitHub

```text
Repositório
└── ryo-yamada-beta
    ├── index.html
    ├── atualizacoes.html
    └── README.md
```

### Cloudflare Pages

```text
GitHub
   ↓
Cloudflare Pages
   ↓
Deploy automático
   ↓
Site
```

### Para publicar uma atualização

```text
Editar atualizacoes.html
        ↓
Commit no GitHub
        ↓
Cloudflare publica automaticamente
```

Você não precisa desligar o site.
