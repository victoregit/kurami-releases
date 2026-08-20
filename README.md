<div align="center">
  <img src="./iconapp.png" width="150" alt="Kuromi Helper">

  # Kuromi Helper

  **Seu conteúdo vira um estudo completo, organizado e feito para você.**

  Um aplicativo de estudos com inteligência artificial para criar resumos, flashcards, simulados e reforços personalizados a partir de um assunto ou material enviado.

  ![Versão](https://img.shields.io/badge/versão-1.0.2-f28bb8?style=for-the-badge)
  ![Plataformas](https://img.shields.io/badge/Android%20%7C%20iOS%20%7C%20Windows-2d2430?style=for-the-badge)
  ![Status](https://img.shields.io/badge/status-beta-cb8cff?style=for-the-badge)
</div>

---

## Baixar o Kuromi Helper

| Plataforma | Versão | Download |
|---|---:|---|
| Android | 1.0.2 Beta | [Baixar APK](https://github.com/victoregit/kurami-releases/releases/latest/download/Kuromi-Helper-Android-Beta-1.0.2.apk) |
| Windows — Instalador | 1.0.2 | [Baixar Setup](https://github.com/victoregit/kurami-releases/releases/latest/download/Kuromi-Helper-Setup-1.0.2-x64.exe) |
| Windows — Portátil | 1.0.2 | [Baixar Portable](https://github.com/victoregit/kurami-releases/releases/latest/download/Kuromi-Helper-Portable-1.0.2-x64.exe) |
| iPhone/iPad | 1.0.2 Beta | [Baixar IPA](https://github.com/victoregit/kurami-releases/releases/latest/download/Kuromi-Helper-iOS-unsigned.ipa) |

> Os links passam a funcionar depois que os arquivos forem anexados à release mais recente do GitHub. O IPA é uma build sem assinatura da App Store e precisa ser instalado por sideload.

[Ver todas as versões e notas de atualização](https://github.com/victoregit/kurami-releases/releases)

---

## O que é o Kuromi Helper?

O Kuromi Helper é um aplicativo mobile-first criado para tornar o estudo mais simples, rápido e menos cansativo. Em vez de abrir várias páginas, organizar anotações manualmente e montar perguntas uma por uma, a pessoa informa o que precisa estudar e recebe um material completo dentro do próprio aplicativo.

É possível começar apenas digitando um assunto, como **fotossíntese**, **Revolução Francesa** ou **funções de segundo grau**. Também é possível anexar conteúdos que a pessoa já possui — PDFs, imagens de uma matéria, resumos, apostilas ou arquivos de texto — para que o estudo seja elaborado com base naquele material.

O resultado não é somente uma resposta de chat. O conteúdo é separado em partes próprias para aprender e revisar:

- explicação e resumo do assunto;
- pontos mais importantes da matéria;
- fontes para aprofundamento;
- imagens relacionadas quando disponíveis;
- flashcards para memorização;
- simulado para testar o aprendizado;
- análise de pontos fortes e fracos;
- novo reforço criado com base nos erros.

Tudo fica ligado à conta que está conectada. Dessa forma, cada pessoa possui seu próprio histórico, seus estudos recentes e sua própria chave da API Gemini no backend.

## Como funciona?

### 1. Entre na sua conta

O login é feito pelo Supabase. Os estudos e o histórico pertencem ao usuário autenticado, portanto uma conta não acessa os materiais particulares de outra.

### 2. Escolha um assunto ou envie seu material

Digite o tema na barra principal ou use o botão `+` para anexar até cinco arquivos. O limite combinado é de 8 MB e são aceitos:

- documentos PDF;
- imagens de páginas, exercícios ou anotações;
- arquivos TXT e Markdown.

### 3. Receba o estudo organizado

O backend identifica o usuário, seleciona sua chave Gemini protegida no Supabase e solicita a criação do conteúdo. Quando necessário, o app também procura fontes e imagens complementares na Wikimedia.

### 4. Revise com flashcards

Os conceitos principais são transformados em cartões de pergunta e resposta. Eles permitem revisar o conteúdo de maneira curta e repetível, especialmente antes de provas.

### 5. Faça o simulado

O simulado mede quais partes foram compreendidas e quais ainda precisam de atenção. Ao terminar, o aplicativo apresenta o resultado em vez de apenas mostrar uma nota isolada.

### 6. Reforce os pontos fracos

Com base nos acertos e erros, o Kuromi Helper destaca os pontos fortes, identifica dificuldades e pode montar um novo simulado direcionado para aquilo que precisa ser reforçado.

### 7. Continue de onde parou

Os estudos recentes permanecem salvos na conta. Abrir novamente um estudo já criado carrega o conteúdo armazenado e não faz outra solicitação ao Gemini, evitando gasto repetido de tokens.

## Principais recursos

### Estudo criado por IA

O Gemini transforma um tema amplo ou um material enviado em conteúdo estruturado. A integração acontece por uma Edge Function, portanto nenhuma chave privada é colocada dentro do aplicativo instalado.

### Chave Gemini individual por usuário

Cada UID pode ser associado a uma chave própria. Isso impede que todas as contas consumam a mesma cota e mantém o uso de cada pessoa separado.

### Economia de tokens

Assuntos genéricos podem utilizar um cache compartilhado quando um estudo equivalente já existe. Estudos feitos com anexos particulares nunca entram nesse cache. Reabrir um item do histórico também não gera o conteúdo novamente.

### Estudos salvos por conta

Histórico, estudos recentes e sugestões relacionadas acompanham a conta conectada. O conteúdo não depende somente do dispositivo em que o aplicativo foi aberto.

### Materiais próprios

O usuário não precisa depender apenas de uma pesquisa por assunto. Apostilas, páginas fotografadas, exercícios e anotações podem servir como base direta para o estudo.

### Experiência multiplataforma

A interface foi pensada primeiro para telas de celular e depois adaptada para computador. O mesmo projeto atende:

- Android por meio do Capacitor;
- iPhone e iPad por meio do Capacitor e Codemagic;
- Windows por meio do Electron;
- navegador durante o desenvolvimento e testes.

### Visual personalizável

O aplicativo utiliza uma identidade kawaii, fonte arredondada, personagens, tons pastéis e dois modos visuais:

- **Claro:** interface suave, clara e rosada;
- **Escuro:** cores escuras com contraste confortável.

## Privacidade e segurança

- chaves Gemini ficam em secrets da Edge Function;
- o aplicativo identifica a chave pelo UID autenticado;
- senhas são tratadas pelo sistema de autenticação do Supabase;
- anexos particulares não são colocados no cache público;
- variáveis privadas não fazem parte dos instaladores;
- estudos são separados por conta com as políticas do banco.

> A publishable key do Supabase pode existir no cliente. A proteção dos dados depende da autenticação e das políticas RLS configuradas no projeto.

## Instalação

### Android

1. Baixe o arquivo `.apk` na seção de download.
2. Abra o arquivo no celular.
3. Autorize a instalação de aplicativos dessa fonte, caso o Android solicite.
4. Conclua a instalação e abra o Kuromi Helper.

A build 1.0.2 é uma versão beta assinada para testes e ainda não é uma publicação da Play Store.

### Windows

Use o **Setup** para instalar normalmente e criar atalhos. A versão **Portable** abre sem instalação e pode ser mantida em qualquer pasta.

Como o aplicativo ainda não possui certificado comercial de assinatura de código, o Windows SmartScreen pode exibir um aviso de editor desconhecido.

### iPhone e iPad

O arquivo IPA atual é produzido pelo Codemagic sem assinatura da App Store. Para testes, ele precisa ser assinado e instalado com uma ferramenta de sideload, como o Sideloadly, usando um Apple ID.

## Executar o projeto localmente

### Requisitos

- Node.js 22 ou mais recente;
- pnpm 11;
- Android Studio para builds Android;
- conta no Codemagic para builds iOS sem Mac.

Se o PowerShell não reconhecer o pnpm:

```powershell
corepack enable
corepack prepare pnpm@11.19.0 --activate
```

Instale as dependências e inicie:

```powershell
pnpm install --frozen-lockfile
pnpm dev
```

Abra o endereço exibido pelo Vite. Normalmente será `http://localhost:5173`, mas outra porta poderá ser utilizada se ela já estiver ocupada.

## Configuração do Supabase

Copie `.env.example` para `.env` e preencha apenas as informações públicas:

```env
VITE_SUPABASE_URL=https://seu-projeto.supabase.co
VITE_SUPABASE_PUBLISHABLE_KEY=sb_publishable_sua-chave-publica
VITE_STUDY_API_URL=https://seu-projeto.supabase.co/functions/v1/generate-study
```

As chaves Gemini devem permanecer no secret `GEMINI_API_KEYS_BY_USER` da Edge Function, associadas pelo UID:

```json
{
  "uid-do-usuario-1": "chave-gemini-do-usuario-1",
  "uid-do-usuario-2": "chave-gemini-do-usuario-2"
}
```

Nunca coloque chaves Gemini, senhas ou service-role keys em variáveis `VITE_*`, no código-fonte ou no instalador.

## Gerar os aplicativos

### Windows

```powershell
pnpm desktop:package
```

### Android

```powershell
pnpm mobile:sync
Set-Location android
.\gradlew.bat assembleDebug
```

### iOS pelo Codemagic

O repositório inclui o workflow `ios-free-sideload` em `codemagic.yaml`. Depois de conectar o repositório ao Codemagic, execute esse workflow e baixe `Kuromi-Helper-iOS-unsigned.ipa` nos artefatos.

## Estrutura do projeto

```text
src/                         interface e regras do aplicativo
public/assets/               imagens usadas no app
assets-source/               artes originais e arquivos de trabalho
android/                     projeto nativo Android
ios/                         projeto nativo iOS
electron/                    aplicativo Windows
supabase/functions/          backend seguro de geração com IA
docs/                        documentação e notas das versões
codemagic.yaml               workflow remoto do iOS
```

## Versão atual

Consulte as mudanças da versão em [RELEASE_NOTES_1.0.2.md](docs/RELEASE_NOTES_1.0.2.md).

## Aviso sobre as artes

Este é um projeto de uso privado. Personagens, nomes e marcas de terceiros pertencem aos respectivos detentores. Antes de qualquer distribuição pública ou comercial, as artes devem ser substituídas ou devidamente licenciadas.

---

<div align="center">
  <strong>Kuromi Helper 1.0.2</strong><br>
  Feito para deixar a rotina de estudos mais leve, organizada e bonita.
</div>
