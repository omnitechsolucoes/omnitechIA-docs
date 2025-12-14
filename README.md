# White‑Label da Documentação (Mintlify)

A **Omnitech** é uma empresa de tecnologia especializada em **soluções de comunicação digital e omnichannel**, oferecendo recursos como Discador Automático, PABX Virtual, URA Inteligente, Chatbot, Atendimento Omnichannel, SMS, RCS, VoIP e integrações via API.

Dentre essas soluções, o modelo white-label abordado nesta documentação refere-se exclusivamente à Plataforma de Chamadas Automatizadas com IA da Omnitech, permitindo que parceiros e clientes utilizem essa solução específica com sua própria marca, identidade visual e domínio.

A documentação também pode ser personalizada (white-label), garantindo uma experiência totalmente alinhada à identidade do parceiro ou cliente final.

Este guia explica como criar uma versão personalizada da documentação da Omnitech utilizando o Mintlify, aplicando sua marca (cores, logotipos e nome), publicando em um subdomínio Mintlify ou domínio próprio e, por fim, vinculando a URL da documentação ao painel administrativo da plataforma de chamadas automatizadas com IA.
---

## O que será configurado

* Um novo repositório GitHub sob sua organização, contendo a documentação da Omnitech
* Aplicação da sua identidade visual via `mint.json` (nome, cores, logotipos e favicon)
* Documentação publicada em um subdomínio Mintlify ou domínio personalizado
* URL final da documentação configurada no painel administrativo da Omnitech

---

## Pré‑requisitos

* Conta ou organização no GitHub com permissão para criar repositórios
* Conta no Mintlify com acesso para criar um site e conectar um repositório GitHub
* Conhecimento básico de Git

---

## 1) Criar o repositório no GitHub

Escolha uma das opções abaixo para criar o repositório da documentação.

### Opção A — Usar este repositório como template (recomendado)

1. No GitHub, clique em **Use this template** (ou **Create a new repository from template**).
2. Defina o nome do novo repositório dentro da sua organização.

### Opção B — Importar o repositório

1. No GitHub, acesse **Import repository**.
2. Cole a URL deste repositório e realize a importação.

---

## 2) Executar a documentação localmente (opcional, porém recomendado)

Instale o CLI do Mintlify e execute a pré‑visualização local a partir da raiz do repositório, onde está o arquivo `mint.json`.

```bash
npm i -g mintlify
mintlify install
mintlify dev
```

A documentação ficará disponível no endereço exibido no terminal.

---

## 3) Aplicar a identidade visual da Omnitech no `mint.json`

Edite o arquivo `mint.json` na raiz do repositório e ajuste os campos de marca conforme a identidade da Omnitech.

Exemplo:

```json
{
  "name": "Omnitech Docs",
  "favicon": "/favicon.png",
  "logo": "/resources/logo-light.svg",
  "logoDark": "/resources/logo-dark.svg",
  "colors": {
    "primary": "#12428A",
    "light": { "primary": "#12428A" },
    "dark": { "primary": "#8FA9D6" }
  }
}
```

Observações:

* **name**: Nome exibido na documentação.
* **logo / logoDark**: Logotipos da Omnitech para fundo claro e escuro.
* **favicon**: Ícone da documentação.
* **colors.primary**: Cor primária da Omnitech.

Outros campos como navegação, links de rodapé, redes sociais e analytics podem ser ajustados conforme a necessidade.

---

## 4) Substituir logotipos e assets

* Substitua o arquivo `favicon.png` pelo favicon da Omnitech.
* Adicione os logotipos em `resources/` (ex.: `logo-light.svg` e `logo-dark.svg`).
* Confirme se os caminhos configurados no `mint.json` correspondem aos arquivos reais.

Dica: prefira arquivos SVG para melhor qualidade visual.

---

## 5) (Opcional) Ajustar navegação e metadados

Revise campos como:

* `navigation`
* `footerLinks`
* `topbarLinks`
* `github`
* `ogImage`

Esses itens ajudam a alinhar a documentação com a estrutura e posicionamento da Omnitech.

---

## 6) Conectar o repositório ao Mintlify e publicar

1. Acesse o painel do Mintlify e crie um novo site.
2. Conecte sua conta GitHub e selecione o repositório da documentação.
3. Defina o branch padrão (normalmente `main`).
4. Escolha o subdomínio (ex.: `docs.omnitech.mintlify.site`).
5. Clique em **Deploy**.

### Domínio personalizado (opcional)

É possível usar um domínio próprio, como `docs.omnitech.com.br`, configurando um CNAME conforme instruções do Mintlify.

---

## 7) Vincular a URL da documentação ao painel da Omnitech

Após a publicação:

1. Copie a URL final da documentação.
2. Acesse o painel administrativo da Omnitech.
3. Vá em **Configurações → White‑Label / Branding**.
4. Informe a URL da documentação e salve.

Isso permitirá que seus usuários acessem a documentação diretamente pela plataforma.

---

## 8) Atualizações contínuas

* Edite os arquivos `.mdx` e o `mint.json` conforme necessário.
* Utilize `mintlify dev` para pré‑visualizar alterações.
* Realize commit e push no branch principal para publicação automática.

---

## Solução de problemas

* **`mintlify dev` não inicia**: execute `mintlify install` novamente.
* **Erro 404 local**: confirme se está na raiz do repositório.
* **Marca não atualiza**: valide os caminhos dos arquivos no `mint.json`.
* **Deploy não refletiu mudanças**: verifique se o repositório e branch corretos estão conectados no Mintlify.
