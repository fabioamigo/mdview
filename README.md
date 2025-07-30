# mdview

> Visualizador de **Markdown colorido** para o terminal – rápido, _zero‑dependência_ de binários nativos, pronto para Linux, macOS e WSL.  
> Construído sobre [Rich](https://rich.readthedocs.io/) + [Pygments](https://pygments.org/).

---

## ✨ Destaques

| Recurso | Como funciona |
|---------|---------------|
| **Sintaxe colorida** | Blocos de código realçados via Pygments. |
| **Sem fundo branco** | Renderiza usando o fundo atual do seu terminal. |
| **Pager integrado** | Usa o pager definido em `$PAGER` (padrão `less -RFX`). |
| **Pipeline‑friendly** | Lê arquivo ou `stdin`, pode desativar cores/pager. |
| **Catálogo de temas** | `--list-themes` mostra preview de todos os estilos disponíveis. |
| **Instalação leve** | Apenas Rich (≈ 400 KB) + Pygments; nada compilado. |

---

## 🚀 Instalação

### 1. Crie o ambiente (recomendado)

```bash
conda create -y -n mdview python=3.12
conda activate mdview
````

### 2. Instale dependências com **pip**

```bash
pip install "rich[markdown]"
```

### 3. Baixe o script

```bash
curl -o mdview https://raw.githubusercontent.com/fabioamigo/mdview/main/mdview
chmod +x mdview
mv mdview ~/.local/bin/           # opcional, adiciona ao PATH
```

> **Dica:** adicione `~/.local/bin` ao seu `PATH` se ainda não estiver lá.

---

## 🖥️ Uso básico

```bash
mdview README.md                  # visualiza arquivo
mdview README.md --theme dracula  # escolhe tema de código
mdview --list-themes              # prévia de TODOS os temas
```

| Flag            | Descrição                                                              |
| --------------- | ---------------------------------------------------------------------- |
| `file` (`-`)    | Caminho do `.md` ou `-` para ler do *stdin*.                           |
| `--theme`       | Qualquer tema listado em `--list-themes` (padrão `monokai`).           |
| `--list-themes` | Mostra preview de todos os temas com o mesmo pipeline de renderização. |
| `--no‑pager`    | Imprime direto no `stdout` (ideal para redirecionar).                  |
| `--no‑color`    | Remove sequências ANSI (copia/cola limpo).                             |

### Exemplos

```bash
# Visualizar um README remoto
curl -s https://raw.githubusercontent.com/tiangolo/fastapi/master/README.md | mdview -

# Mostrar apenas um trecho (linhas 30–90)
mdview --no-pager README.md | sed -n '30,90p'

# Script no Vim/Neovim: :%!mdview - --no-pager
```

---

## 🔧 Personalização

* **Pager:** defina `PAGER="less -RFX"` (ou seu preferido) no `.bashrc`/`.zshrc`.
* **Cores:** escolha `--theme gruvbox-dark` ou `--theme tango` etc.
* **Aliases:**

```bash
alias mdv="mdview --theme gruvbox-dark"
alias mdl="mdview --list-themes --no-pager | less -R"
```

---

## 🧪 Rodando testes

O projeto inclui um script rudimentar de CI para checar:

```bash
bash tests/run.sh    # lint + execução básica
```

---

## 📜 Licença

[MIT](LICENSE)

---

## 🙋 Contribuindo

1. Faça um *fork* do projeto.
2. Crie sua *feature branch*: `git checkout -b minha-feature`.
3. Envie *pull request* depois de passar nos testes: `pytest`.

Feedback, novas ideias e correções são muito bem‑vindos. 🚀

---

<sub>Feito com ❤️ em Arch Linux.</sub>

```
::contentReference[oaicite:0]{index=0}
```
