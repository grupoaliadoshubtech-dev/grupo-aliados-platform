# Grupo Aliados Hub Tech — Plataforma de Soluções

Repositório unificado das landing pages institucionais, comerciais e documentações públicas do ecossistema **Grupo Aliados Hub Tech**.

---

## 📁 Estrutura do Repositório

```text
grupo-aliados-platform/
├── index.html                  # Hub principal do ecossistema Aliados
├── apex/
│   └── index.html              # Landing page comercial: Apex GNRE SaaS
├── comagente/
│   └── index.html              # Landing page comercial: ComAgente (WhatsApp IA + CRM)
├── docs/                       # Documentações públicas e manuais
│   ├── apex/
│   │   └── README.md           # Guia funcional e modelos do Apex GNRE
│   └── comagente/
│       └── README.md           # Guia funcional e modelos do ComAgente
├── vercel.json                 # Configuração de URLs limpas e cabeçalhos na Vercel
├── .gitignore                  # Proteção contra arquivos sensíveis e temporários
└── README.md                   # Documentação geral do repositório
```

---

## 🚀 Soluções Integradas

### 1. Hub Principal (`/`)
- **Objetivo**: Portal de entrada unificado para clientes, parceiros e investidores, apresentando as soluções de automação fiscal e inteligência de atendimento.

### 2. Apex GNRE SaaS (`/apex`)
- **Objetivo**: Automação ponta a ponta na emissão de guias GNRE em lote a partir do XML da NF-e, transmissão mTLS SEFAZ e geração de remessa bancária Itaú SISPAG (CNAB 240).
- **Documentação pública**: Consulte [`docs/apex/README.md`](docs/apex/README.md).

### 3. ComAgente (`/comagente`)
- **Objetivo**: Plataforma de atendimento inteligente via WhatsApp, combinando inteligência artificial, transbordo contextual para equipe humana (handoff), CRM integrado e métricas operacionais.
- **Documentação pública**: Consulte [`docs/comagente/README.md`](docs/comagente/README.md).

---

## 🔒 Segurança e Isolamento dos Sistemas

Este repositório foi concebido estritamente para **páginas estáticas comerciais e documentações públicas**:
- Os repositórios de software das aplicações (**`aliados-apex`** e **`Com_Agente`**) permanecem **100% isolados e independentes**, mantendo seus bancos de dados, chaves mTLS, workers, APIs e deploys de produção (Railway, Supabase) intocados.
- Nenhum código de backend ou variável de ambiente confidencial trafega ou é armazenado neste repositório.

---

## 💻 Como Visualizar e Testar Localmente

Você pode abrir qualquer arquivo HTML diretamente no seu navegador ou iniciar um servidor web local para testar a navegação completa:

### Opção 1: Python
```bash
python -m http.server 3000
```
Acesse no navegador:
- Hub: `http://localhost:3000/`
- Apex: `http://localhost:3000/apex/`
- ComAgente: `http://localhost:3000/comagente/`

### Opção 2: Node.js (npx serve)
```bash
npx serve .
```

---

## 🌐 Deploy na Vercel

O projeto conta com arquivo [`vercel.json`](vercel.json) pré-configurado com:
- `cleanUrls: true`: rotas acessíveis sem a extensão `.html` (ex: `/apex` e `/comagente`).
- Cabeçalhos de segurança HTTP (`X-Frame-Options`, `X-Content-Type-Options`, `X-XSS-Protection`).

### Passos de Publicação Segura:
1. Conecte este repositório (`grupo-aliados-platform`) à sua conta na Vercel.
2. Cada commit ou Pull Request na branch de revisão gerará automaticamente um **Deployment de Preview**.
3. Realize a homologação e testes no link de preview antes de promover a branch principal para produção.
