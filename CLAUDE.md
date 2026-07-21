CLAUDE.md — Landing Page Adilio Terra (Advocacia Imobiliária)
Este arquivo orienta o Claude Code em todo trabalho neste repositório. Leia antes de qualquer alteração.
Contexto do projeto
	•	Cliente: Adilio Terra, advogado especializado em direito imobiliário.
	•	Objetivo: landing page de captação de leads (regularização de imóvel, usucapião, inventário, retificação de matrícula, adjudicação compulsória, due diligence).
	•	Personas: proprietários, compradores, herdeiros, investidores.
	•	Referência de estrutura: guia em 10 seções (hero, serviços, dores, como funciona, diferenciais, sobre o advogado, FAQ, casos resolvidos, CTA final, rodapé).
Stack técnica
	•	Frontend: site estático (HTML/CSS/JS), hospedado no Cloudflare Pages.
	•	Backend de captura: Cloudflare Pages Function (serverless), sem servidor dedicado.
	•	Banco de dados: Firestore, collection leads.
	•	Notificação de novo lead: e-mail (Resend/SendGrid) e/ou webhook para o WhatsApp do Adilio.
Fluxo de trabalho (igual ao Planni)
	1.	Claude Code faz as alterações de código e abre Pull Request.
	2.	Vitor revisa e faz merge.
	3.	Cloudflare Pages faz deploy automático a partir da main.
	4.	Nunca commitar chaves de API ou credenciais no código — usar variáveis de ambiente/secrets do Cloudflare. Se uma credencial vazar no chat ou em um commit, revogar e rotacionar imediatamente.
Regras de compliance — OAB (Provimento 205/2021)
Proibido:
	•	Exibir valores ou faixas de honorários.
	•	Superlativos (“o melhor advogado da cidade”, “especialista nº1”).
	•	Promoções, descontos, senso de urgência comercial (“vagas limitadas”).
	•	Explorar emocionalmente a dor do cliente (herança, perda, litígio).
	•	Depoimentos nominais de clientes sem consentimento expresso e documentado.
Permitido e recomendado:
	•	Tom informativo e sóbrio.
	•	FAQ sobre “como funciona a cobrança dos honorários” (sem valores).
	•	Casos resolvidos descritos de forma genérica, sem identificar o cliente.
Qualquer copy nova deve ser revisada contra esta lista antes de ir para produção.
LGPD
	•	Checkbox de consentimento explícito no formulário, próximo ao botão de envio — não apenas um link no rodapé.
	•	Página de Política de Privacidade real e acessível (não placeholder).
	•	Campo de descrição da situação é dado sensível pelo contexto jurídico: tratar com o mesmo cuidado que dado de saúde.
Estrutura de dados — Firestore
Collection: leads
