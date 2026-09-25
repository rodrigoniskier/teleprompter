# Mobile Teleprompter

### Câmera, roteiro e gravação em uma única tela — direto no navegador

Este projeto é um **teleprompter mobile-first** construído apenas com tecnologias nativas da web. Ele permite abrir a câmera, colar um roteiro, controlar a velocidade da rolagem e gravar a apresentação sem depender de backend.

Foi pensado para funcionar como uma ferramenta rápida para gravação de vídeos pelo celular.

## Recursos

- câmera frontal ou traseira;
- texto sobreposto à imagem da câmera;
- rolagem automática do roteiro;
- controle de velocidade;
- controle do tamanho da fonte;
- layout sobreposto ou tela dividida;
- espelhamento da câmera;
- modo tela cheia;
- gravação pelo navegador;
- download local do vídeo ao concluir;
- persistência do texto e preferências no `localStorage`;
- Wake Lock quando suportado;
- PWA com manifest e service worker;
- interface adaptada a portrait e landscape.

## Privacidade

O roteiro é salvo apenas no armazenamento local do navegador.

A aplicação não possui backend próprio e não envia o texto para um servidor. A captura da câmera/microfone depende exclusivamente das permissões concedidas pelo usuário ao navegador.

## Tecnologias

- HTML5
- CSS
- JavaScript
- MediaDevices / `getUserMedia`
- MediaRecorder
- Fullscreen API
- Wake Lock API
- Local Storage
- Service Worker / PWA

## Executar

Por utilizar APIs de câmera e microfone, o ideal é servir o projeto em um contexto seguro (`https://`) ou em `localhost`.

Exemplo:

```bash
git clone https://github.com/rodrigoniskier/teleprompter.git
cd teleprompter
python -m http.server 8000
```

Depois acesse:

```text
http://localhost:8000
```

## Decisão de arquitetura

O projeto intencionalmente não utiliza framework ou backend. Todo o fluxo cabe no navegador:

```text
Roteiro local
     +
Câmera / microfone
     ↓
Teleprompter no navegador
     ↓
MediaRecorder
     ↓
Arquivo de vídeo local
```

Isso mantém a aplicação pequena, fácil de publicar e adequada para uso rápido no celular.

## Por que este projeto está no portfólio

É um exemplo de como uma necessidade prática pode ser resolvida com uma arquitetura mínima, explorando bem as **APIs modernas do navegador** em vez de adicionar infraestrutura desnecessária.

---

Desenvolvido por [Rodrigo Niskier](https://github.com/rodrigoniskier).
