<div align="center">

<img src="assets/optimizer-logo.svg" alt="Optimizer Skill logo" width="144">

# Optimizer Skill

### O caminho mais simples e seguro para melhorar seu código com IA.

Uma skill profissional para **Claude Code** que encontra ganhos reais de performance,
clareza e organização — sem reescritas especulativas.

[![Claude Code](https://img.shields.io/badge/Claude%20Code-plugin-D97757?logo=anthropic&logoColor=white)](https://docs.anthropic.com/en/docs/claude-code)
[![Version](https://img.shields.io/badge/version-1.0.0-6E56CF)](https://github.com/HenriqueMirandaa/optimizer-skill/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT-2ea44f)](LICENSE)

</div>

## Por que usar?

Assistentes de IA podem “otimizar” código adicionando abstrações, dependências e
complexidade sem provar que houve ganho. A **Optimizer Skill** impõe um processo
mais confiável:

> **Entender → medir → mudar o mínimo → verificar → explicar as evidências**

Ela é útil para refatoração, revisão de código, gargalos de performance,
organização de módulos e limpeza técnica.

## Instalação

### Opção recomendada: marketplace do seu repositório

No terminal do Claude Code:

```text
/plugin marketplace add HenriqueMirandaa/optimizer-skill
/plugin install optimizer-skill@optimizer-skill-marketplace
```

Ou pelo terminal do sistema:

```bash
claude plugin marketplace add HenriqueMirandaa/optimizer-skill
claude plugin install optimizer-skill@optimizer-skill-marketplace
```

Escolha o escopo desejado durante a instalação:

| Escopo | Disponibilidade |
| --- | --- |
| `user` | Todos os seus projetos nesta máquina |
| `project` | Colaboradores deste repositório |
| `local` | Apenas você neste repositório |

### Testar sem instalar

Clone o projeto e execute:

```bash
claude plugin validate .
claude --plugin-dir .
```

Para testar um release ZIP em uma única sessão:

```bash
claude --plugin-url https://github.com/HenriqueMirandaa/optimizer-skill/releases/download/v1.0.0/optimizer-skill.zip
```

## Como usar

Depois da instalação, invoque:

```text
/optimizer-skill:optimizer-skill
```

Ou peça naturalmente:

```text
Use a optimizer-skill neste módulo. Encontre o maior ganho real,
meça antes e faça a menor alteração segura.
```

O Claude deve retornar:

1. **Finding** — o problema encontrado;
2. **Change** — a menor mudança eficaz;
3. **Evidence** — testes e medições;
4. **Tradeoffs** — impactos e limitações;
5. **Skipped** — o que foi conscientemente deixado de fora.

## Princípios

- Medir antes de otimizar.
- Remover trabalho desnecessário antes de adicionar mecanismos.
- Preferir bibliotecas padrão, helpers existentes e recursos nativos.
- Corrigir a causa compartilhada, não cada sintoma.
- Preservar segurança, validação, acessibilidade e tratamento de erros.
- Não adicionar cache, dependência ou abstração sem justificativa.
- Não alegar ganho de performance sem evidência.

## Estrutura

```text
.
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── skills/
│   └── optimizer-skill/
│       ├── SKILL.md
│       └── examples/
├── assets/
│   └── optimizer-logo.svg
├── LICENSE
└── README.md
```

## Desenvolvimento

Requisitos:

- Claude Code instalado e autenticado;
- Git;
- acesso ao GitHub, caso queira publicar alterações.

Valide o plugin antes de abrir um release:

```bash
claude plugin validate .
```

O projeto não executa código próprio, não instala dependências e não requer
servidor MCP. A skill é composta por instruções Markdown carregadas quando
invocada.

## Licença

Distribuído sob a licença [MIT](LICENSE).
