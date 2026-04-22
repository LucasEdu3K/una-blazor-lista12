div align="center">

# 🌱 EcoMonitor

**Painel de Gamificação Sustentável**

*Prova de Conceito desenvolvida com Blazor Interactive Server (.NET 8)*

[![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?style=flat-square&logo=dotnet)](https://dotnet.microsoft.com/)
[![Blazor](https://img.shields.io/badge/Blazor-Interactive_Server-512BD4?style=flat-square&logo=blazor)](https://dotnet.microsoft.com/apps/aspnet/web-apps/blazor)
[![Licença](https://img.shields.io/badge/Licença-Acadêmica-green?style=flat-square)](LICENSE)

</div>

---

## 📋 Identificação

| Campo | Informação |
|---|---|
| **Nome** | Lucas Eduardo C. do Nascimento |
| **Curso** | Ciência da Computação — Centro Universitário UNA Contagem |
| **Disciplina** | Interação Humano-Computador e UX |
| **Professor** | Daniel Henrique Matos de Paiva |
| **Projeto** | Lista 12 — Componentização e Estado com Blazor |

---

## 💡 Sobre o Projeto

O **EcoMonitor** é um sistema de gamificação desenvolvido para a ONG fictícia **ReCiclo**, onde o usuário registra ações sustentáveis e acompanha seu impacto ambiental em tempo real.

A aplicação demonstra o uso de **componentes reutilizáveis no Blazor** por meio do componente `EcoStatus.razor`, aplicando os princípios de componentização e gerenciamento de estado independente.

---

## ✨ Funcionalidades

- ♻️ **Três instâncias** do componente `EcoStatus` com pesos diferentes por ação
- 🔢 **Contador individual** por tipo de ação sustentável
- 🎨 **Estilização condicional** — o texto muda de cor ao ultrapassar 50 pontos
- 📊 **Barra de progresso** visual que avança conforme o contador cresce *(desafio extra)*
- 🏆 **Mensagem de conquista** ao atingir 100 pontos *(desafio extra)*

---

## 🎯 Heurísticas de Nielsen Aplicadas

### 1. Visibilidade do Status do Sistema

O contador de pontos é atualizado **imediatamente** a cada clique, sem atraso ou necessidade de recarregar a página. O usuário sempre sabe exatamente quanto já acumulou — o feedback é instantâneo e claro.

### 2. Reconhecimento em vez de Memorização

Cada instância do componente exibe o nome da ação (ex: *"Reciclagem de Plástico"*) e o peso associado diretamente na interface. O usuário não precisa lembrar o que cada botão faz — a informação está sempre visível.

---

## 🚀 Como Executar

### Pré-requisitos

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- Terminal (PowerShell, bash ou similar)

### Passo a passo

```bash
# 1. Clone o repositório
git clone https://github.com/[seu-usuario]/una-blazor-lista12.git

# 2. Acesse a pasta do projeto
cd una-blazor-lista12/EcoMonitor

# 3. Execute com o perfil HTTPS
dotnet run --launch-profile https
```

Acesse no navegador: **https://localhost:5001**

> **⚠️ Aviso de certificado:** Se o navegador alertar sobre certificado, clique em *"Avançado"* → *"Continuar"*.  
> Para confiar no certificado de desenvolvimento: `dotnet dev-certs https --trust`

---

## 🧩 Como o `[Parameter]` foi utilizado

O parâmetro é o que torna o componente verdadeiramente **reutilizável**. Em vez de criar três componentes distintos, um único `EcoStatus.razor` aceita valores externos via `[Parameter]`:

```razor
@* EcoStatus.razor *@

[Parameter] public string NomeAcao { get; set; } = "Ação";
[Parameter] public int PesoAcao   { get; set; } = 1;
[Parameter] public int Meta       { get; set; } = 50;
```

Na `Home.razor`, o mesmo componente é chamado três vezes com configurações diferentes:

```razor
<EcoStatus NomeAcao="Reciclagem de Plástico"  PesoAcao="1"  />
<EcoStatus NomeAcao="Plantio de Árvores"      PesoAcao="10" />
<EcoStatus NomeAcao="Descarte de Eletrônicos" PesoAcao="5"  />
```

Cada instância mantém seu próprio **estado interno** (`total`) completamente independente das outras. Esse é o princípio central de componentização: *escreve-se uma vez, usa-se quantas vezes quiser com comportamentos distintos.*

---

## 📁 Estrutura do Projeto

```
EcoMonitor/
├── Components/
│   ├── Pages/
│   │   └── Home.razor          # Página principal com as 3 instâncias
│   └── EcoStatus.razor         # Componente reutilizável
├── wwwroot/
│   └── app.css                 # Estilos globais
├── Program.cs
└── EcoMonitor.csproj
```

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Descrição |
|---|---|
| **.NET 8** | Plataforma de execução |
| **Blazor Interactive Server** | Framework de UI com renderização server-side |
| **C#** | Linguagem principal |
| **HTML / CSS** | Estrutura e estilização da interface |

---

## 📄 Licença

Projeto acadêmico — uso livre para fins educacionais.

---

<div align="center">
  <sub>Desenvolvido por <strong>Lucas Eduardo C. do Nascimento</strong> · UNA Contagem · 2026</sub>
</div>
