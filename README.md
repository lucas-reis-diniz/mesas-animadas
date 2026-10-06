# Mesas Animadas

Galeria de modelos de painéis de trading animados. Cada modelo é um `index.html` único que roda inteiro no navegador, com mercado, book e agentes inventados.

**Site:** https://lucas-reis-diniz.github.io/mesas-animadas/

| Modelo | O que mostra | Tecnologia |
| --- | --- | --- |
| [Órbita](https://lucas-reis-diniz.github.io/mesas-animadas/orbita/) | Buraco negro com disco de acreção, anel de fótons e lente gravitacional; seis agentes em órbita e um jato a cada trade | Canvas 2D com bloom |
| [Horizonte](https://lucas-reis-diniz.github.io/mesas-animadas/horizonte/) | Estrada synthwave: o sol se põe com a janela de 5 min, os prédios vêm do book e a faixa central acende com o edge | Canvas 2D com bloom |
| [Mente](https://lucas-reis-diniz.github.io/mesas-animadas/mente/) | 120 mil partículas que mudam de forma conforme o agente em foco | WebGL |
| [Mesa Simulada](https://lucas-reis-diniz.github.io/mesas-animadas/mesa-simulada/) | Escritório com bots, funil de memecoins com juiz probabilístico e paper trading | Canvas 2D |

## Como rodar

Não há build. Abra a pasta de um modelo no navegador ou sirva o repositório:

```bash
python3 -m http.server 8000
# depois abra http://localhost:8000/
```

## Estrutura

```
index.html            galeria
orbita/index.html     modelo Órbita
horizonte/index.html  modelo Horizonte
mente/index.html      modelo Mente
mesa-simulada/        modelo Mesa Simulada
assets/               biblioteca de gráficos, fontes e ícone
```

Cada pasta tem um `thumb.jpg` usado na galeria e na prévia de links.

## Ajustes

Nos modelos de BTC (Órbita, Horizonte e Mente) os parâmetros ficam no objeto `CFG` dentro do script da página:

| Campo | Significado |
| --- | --- |
| `edgeMin` | edge mínimo, em probabilidade, para abrir um ticket |
| `kelly` | fração de Kelly usada no sizing |
| `cap` | teto de cada ticket como fração da banca |
| `maxPerWindow` | tickets por janela de 5 min |
| `cooldown` | segundos simulados entre tickets |
| `lag` | atraso do book em segundos; o único edge real da simulação vem daqui |
| `vol` | volatilidade por segundo do preço simulado |

Na Mesa Simulada os limiares ficam no painel da própria página.

## Créditos

- Gráficos de velas e de saldo com [Lightweight Charts](https://github.com/tradingview/lightweight-charts) v4.2.0 (Apache 2.0), servido de `assets/`.
- Fontes Sora, JetBrains Mono e Chakra Petch (SIL Open Font License), servidas de `assets/fonts/`.
- Visual inspirado em painéis de mesas de agentes que circulam no X.

## Aviso

Simulação educativa. Preços, book, agentes e banca são gerados no navegador. Nada aqui é dado de mercado real nem recomendação de investimento.
