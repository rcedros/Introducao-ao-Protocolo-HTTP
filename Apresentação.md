# 📖 Introdução ao Protocolo HTTP – Estrutura de Slides + Sugestões Visuais  

## 🔹 Slide 1 – Abertura  
**Conteúdo:**  
- O que é HTTP  
- Por que estudá-lo além do “funciona”  
- Relevância em **segurança, arquitetura e confiabilidade**  

**Visual:** 🌐 Rede + 🔒 Cadeado  
**Imagem/GIF sugerido:**  
- Ícone de rede conectado a um cadeado  
- GIF: pacotes viajando pela rede até o cadeado se fechar  

**Lab:** —  

## 🔹 Slide 2 – Panorama HTTP/HTTPS  
**Conteúdo:**  
- HTTP = comunicação cliente-servidor  
- HTTPS = camada TLS/SSL  
- Impactos: confiança, risco e arquitetura  

**Visual:** Diagrama cliente → servidor (com e sem 🔒)  
**Imagem/GIF sugerido:**  
- Comparação lado a lado de cliente-servidor sem cadeado (HTTP) e com cadeado (HTTPS)  
- GIF: navegador mostrando 🔓 → 🔒  

**Lab:** Acessar um site em HTTP e HTTPS e inspecionar o cadeado  

## 🔹 Slide 3 – Evolução do Protocolo  
**Conteúdo:**  
- HTTP/1.1 → conexões persistentes, cache  
- HTTP/2 → multiplexação, headers comprimidos  
- HTTP/3 (QUIC) → baixa latência, segurança nativa  

**Visual:** Linha do tempo com ícones ⚡  
**Imagem/GIF sugerido:**  
- Infográfico com HTTP/1.1, HTTP/2, HTTP/3  
- GIF: várias requisições fluindo juntas (multiplexação)  

**Lab:** Testar [tools.keycdn.com/http2-test](https://tools.keycdn.com/http2-test)  

## 🔹 Slide 4 – Métodos HTTP  
**Conteúdo:**  
- GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD  
- Diferença: leitura × alteração × exclusão  
- Idempotência = confiabilidade + segurança  

**Visual:** Tabela (Método | Uso | Idempotente)  
**Imagem/GIF sugerido:**  
- Ícones ilustrando cada método: GET 📄, POST ✍️, PUT 🔄, DELETE 🗑️  
- GIF: GET buscando dados e POST enviando formulário  

**Lab:** Fazer requests via `curl` ou Postman comparando GET vs POST  

## 🔹 Slide 5 – Status Codes  
**Conteúdo:**  
- Classes: 1xx, 2xx, 3xx, 4xx, 5xx  
- Exemplos importantes:  
  - 200 OK  
  - 301 Moved Permanently  
  - 401 Unauthorized vs 403 Forbidden  
  - 429 Too Many Requests  

**Visual:** 🚦 Semáforo  
**Imagem/GIF sugerido:**  
- Semáforo com cores: verde=200, amarelo=300, vermelho=400/500  
- GIF: erro 404 piscando “Page Not Found”  

**Lab:** Rodar `curl -I` em sites diferentes e analisar status  

## 🔹 Slide 6 – Headers  
**Conteúdo:**  
- Comuns: User-Agent, Accept, Content-Type, Cache-Control  
- Segurança: HSTS, CSP, X-Frame-Options, Referrer-Policy  
- Identidade: Authorization + CORS  

**Visual:** Quadro dividido em **comuns** vs **segurança**  
**Imagem/GIF sugerido:**  
- Cabeçalho de carta com labels (User-Agent, Content-Type, etc.)  
- GIF: DevTools mostrando headers de resposta  

**Lab:** Rodar `curl -I https://exemplo.com` e analisar headers  

## 🔹 Slide 7 – Cookies  
**Conteúdo:**  
- O que são e função  
- Tipos: sessão, persistentes, terceiros  
- Atributos de segurança: Secure, HttpOnly, SameSite  
- Riscos: roubo, CSRF, XSS  

**Visual:** 🍪 Cookie com cadeado 🔒  
**Imagem/GIF sugerido:**  
- Cookie dentro de um cofre  
- GIF: cookie sendo roubado (XSS)  

**Lab:** Inspecionar cookies no navegador → DevTools  

## 🔹 Slide 8 – Gerenciamento de Sessão  
**Conteúdo:**  
- Server-side vs Token (JWT)  
- Session fixation, rotação de sessão  
- Logout seguro + invalidação  

**Visual:** Fluxograma sessão (usuário → servidor → token)  
**Imagem/GIF sugerido:**  
- JWT representado como cartão de acesso 🪪  
- GIF: login → servidor gera token → cliente recebe token  

**Lab:** Criar JWT em [jwt.io](https://jwt.io) e decodificar  

## 🔹 Slide 9 – Criptografia e TLS  
**Conteúdo:**  
- Simétrica (AES) × Assimétrica (RSA/ECC)  
- Hashing + assinaturas digitais  
- PKI e cadeia de confiança  
- TLS handshake (1.2 vs 1.3) + PFS  

**Visual:** 🔑 Chaves + certificado digital  
**Imagem/GIF sugerido:**  
- Chave pública + privada trocando dados com certificado  
- GIF: handshake TLS (duas mãos apertando com cadeado)  

**Lab:** `openssl s_client -connect site.com:443`  

## 🔹 Slide 10 – Ataques na Camada HTTP  
**Conteúdo:**  
- Request Smuggling / Desync  
- CSRF  
- Host Header Injection  
- Parameter Pollution  

**Visual:** 🐞 Bug sobre pacote HTTP 📦  
**Imagem/GIF sugerido:**  
- Bug sobre pacote com ícone de alerta ⚠️  
- GIF: usuário clicando → ação CSRF maliciosa executada  

**Lab:** Simular CSRF simples em HTML  

## 🔹 Slide 11 – Logging e Privacidade  
**Conteúdo:**  
- O que logar × não logar (tokens, PII, senhas)  
- Logs estruturados (JSON, trace-id)  
- GDPR/LGPD e retenção  

**Visual:** 📊 Logs com cadeado  
**Imagem/GIF sugerido:**  
- Servidor com logs rolando  
- GIF: log JSON com highlight em “token”  

**Lab:** Criar log JSON em Python com request + trace-id  

## 🔹 Slide 12 – HTTP e OWASP Top 10  
**Conteúdo:**  
- Mapeamento:  
  - Broken Auth  
  - Cryptographic Failures  
  - Security Misconfiguration  
- Controles práticos: rate limit, validação, defaults seguros  

**Visual:** OWASP logo + 🔟 Checklist  
**Imagem/GIF sugerido:**  
- Checklist com marcações verdes ✅  
- GIF: checkmarks aparecendo progressivamente  

**Lab:** Rodar [securityheaders.com](https://securityheaders.com) em site conhecido  

## 🔹 Slide 13 – Conclusão  
**Conteúdo:**  
- Revisão: protocolo, segurança e arquitetura  
- Conexão com confiabilidade  
- Próximos passos: labs avançados, OWASP  

**Visual:** 🚀 Encerramento com call-to-action  
**Imagem/GIF sugerido:**  
- Foguete subindo, simbolizando evolução  
- GIF: desenvolvedor feliz 🎉 ao aplicar boas práticas  

**Lab Final:** Analise seu próprio site com `curl`, DevTools e securityheaders.com  
