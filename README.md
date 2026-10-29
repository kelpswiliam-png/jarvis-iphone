# J.A.R.V.I.S. para iPhone — starter gratuito

## O que já funciona
- Interface futurista responsiva.
- Relógio e data locais.
- Respostas de demonstração para comandos comuns.
- Leitura das respostas em voz alta via voz do navegador.
- Reconhecimento de voz quando o navegador oferece suporte e permite o microfone.
- Campo opcional para conectar um backend de IA.
- Base PWA para instalação pela Tela de Início quando hospedado em HTTPS.

## Limites atuais
Este projeto ainda **não** tem uma IA conectada por padrão. As respostas locais são demonstrações. A voz e o reconhecimento dependem do navegador e das permissões. Ele não consegue criar alarmes do iPhone diretamente, nem ficar escutando continuamente em segundo plano.

## Como testar
1. Extraia o ZIP.
2. Abra `index.html` para testar interface e respostas locais. Alguns recursos, como PWA e microfone, podem exigir HTTPS.
3. Para instalação como web app no iPhone, publique os arquivos em uma hospedagem HTTPS e abra o endereço no Safari. Use Compartilhar → Adicionar à Tela de Início.

## Publicação gratuita
Pode usar uma hospedagem estática com plano gratuito, como GitHub Pages. Os termos e limites dos serviços podem mudar. Faça upload de `index.html`, `manifest.webmanifest` e `sw.js` para o repositório e habilite Pages.

## Conectar IA de forma segura
1. Crie um backend que receba `POST` JSON como `{ "message": "...", "system": "..." }`.
2. O backend deve responder JSON com `{ "reply": "..." }`.
3. No app, informe a URL HTTPS do backend em “Integração de IA”.
4. **Não coloque chaves secretas de API no HTML, JavaScript ou navegador.** A chave deve ficar no ambiente do backend.
5. Use autenticação, limites de uso, validação de entrada e proteção contra abuso.

Um backend pode usar um provedor compatível com chat completions ou um modelo hospedado. Alguns oferecem cotas gratuitas limitadas; disponibilidade, limites e preços precisam ser verificados antes de escolher. Não é possível prometer IA ilimitada e gratuita.

## Integração com recursos do iPhone
Para alarmes e ações do sistema, use Siri e Atalhos separadamente. Uma página web não tem permissão para controlar diretamente todos os apps e funções do iOS. Para automações, crie um atalho com nome “JARVIS” e acione pela Siri.
