# LLZ Garantidora — Painel de Acoes WhatsApp

Painel interativo em HTML puro que consolida a performance das campanhas de recuperacao de credito via WhatsApp da **LLZ Garantidora**.

🔗 **[Ver painel ao vivo](https://SEU-USUARIO.github.io/llz-whatsapp-acoes)**

---

## O que tem no painel

| Aba | O que mostra |
|---|---|
| **Performance Geral** | KPIs da campanha, funil de entrega, disparos por dia, perfil de canal |
| **HSMs vs Controle** | Comparacao direta entre templates segmentados LLZ e base de controle |
| **Calendario** | Visao dia a dia de acoes realizadas e planejadas em junho |
| **Templates HSM** | Todos os templates ativos, metricas e regras de compliance |
| **Piloto Voz** | Publico selecionado para piloto com Moveo.ai (10k clientes) |
| **Diario de Bordo** | Registro cronologico das acoes: objetivo, hipotese e resultado |

---

## Metodologia resumida

### Segmentacao por perfil de canal
Antes de enviar qualquer mensagem, cada cliente e classificado com base no historico de pagamento:

- **SO_DIGITAL** — so pagou via bot ou portal online
- **SO_HUMANO** — so pagou com operador humano
- **MISTO** — usou os dois canais
- **SEM_HISTORICO** — nunca apareceu em nenhuma base de pagamento

Cada perfil recebe um template diferente, com tom e abordagem ajustados.

### Templates UTILITY (Meta/WhatsApp)
Todos os HSMs sao da categoria **UTILITY** (aprovados pelo Meta). Regras:
- Sem valor da divida ou encargos como variavel
- Nenhum template inicia com variavel
- Persona: **Liz** (nome da assistente virtual LLZ)
- Resolucao completa no bot — sem botao para portal externo

### Variavel padrao
```
55PHONE|PrimeiroNome|Condominio|Unidade
```

### Piloto de Voz (Moveo.ai)
10.000 clientes selecionados que nao convertem em canal digital:
- Historico exclusivamente com operador humano
- WhatsApp nao entregou (ERROR) ou nunca foi tentado
- Sem historico de pagamento e divida acima de 365 dias

---

## Como publicar no GitHub Pages

### 1. Crie um repositorio no GitHub
```
Nome sugerido: llz-whatsapp-acoes
Visibilidade: Public (necessario para GitHub Pages gratuito)
```

### 2. Suba o arquivo do painel
```bash
git clone https://github.com/SEU-USUARIO/llz-whatsapp-acoes.git
cd llz-whatsapp-acoes

# Copie o arquivo Dashboard_LLZ_Acoes.html para esta pasta
# Renomeie para index.html
cp Dashboard_LLZ_Acoes.html index.html

git add .
git commit -m "Painel LLZ WhatsApp v1"
git push
```

### 3. Ative o GitHub Pages
- Va em **Settings > Pages**
- Em "Source", selecione **Deploy from a branch**
- Branch: **main**, pasta: **/ (root)**
- Salve — em alguns minutos o link estara ativo

O link sera: `https://SEU-USUARIO.github.io/llz-whatsapp-acoes`

### 4. (Opcional) Deploy automatico com GitHub Actions
Se quiser que o painel seja atualizado automaticamente toda vez que voce subir um novo arquivo, crie o arquivo `.github/workflows/deploy.yml` com o conteudo disponivel neste repositorio.

---

## Atualizacao do painel

Para atualizar numeros quando chegar um novo parquet:

1. Abra `index.html` em qualquer editor de texto
2. Localize as variaveis de dados no `<script>` (procure por `data:`)
3. Substitua os valores
4. Suba o arquivo novamente com `git push`

O painel e atualizado automaticamente em segundos.

---

## Dados e privacidade

O painel contem apenas **dados agregados e anonimizados** (taxas percentuais, totais por segmento). Nenhum dado pessoal de condominios ou moradores e incluido no arquivo HTML.

---

*Campanha Jun/2026 — LLZ Garantidora*
