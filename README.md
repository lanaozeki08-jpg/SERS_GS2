# SERS_GS2

Lana Namie Kano Ozeki - RM 569795
Luan de Araujo Carneiro - RM 573691
Pedro Ribeiro Lopes - RM 570083

# Citizen Assist AI — Energia Sustentável

## Sobre o projeto

O **Citizen Assist AI** é um chatbot educativo que ajuda famílias a compreender o consumo de energia relacionado ao aquecimento de água e a comparar alternativas para reduzir gastos e impactos ambientais.

O estudo de caso compara:

1. **Chuveiro elétrico convencional**;
2. **Redução do tempo de banho e uso de potência econômica**;
3. **Aquecimento solar térmico de água**, mantendo apoio elétrico para a parcela de demanda não atendida pelo sol.

O público-alvo é uma família residencial de referência com quatro moradores, em São Paulo (SP).

> Este projeto é uma simulação educativa. Os valores são estimativas baseadas nas premissas descritas em `premissas_e_calculos.md`, e não substituem uma avaliação técnica da residência ou um orçamento de instalação.

## Objetivos

- Estimar o consumo mensal de energia do chuveiro elétrico;
- Traduzir o consumo em custo financeiro;
- Comparar cenários de economia por mudança de hábitos e aquecimento solar térmico;
- Estimar a redução de emissões associadas à eletricidade consumida;
- Explicar resultados em linguagem simples por meio de uma conversa com IA.

## Como o chatbot funciona

O chatbot utiliza a API da OpenAI com o modelo `gpt-4o-mini`. Quando a pergunta exige cálculos, o modelo pode acionar a ferramenta Python `calcular_consumo_energia`, que executa as fórmulas determinísticas e devolve os resultados para a IA explicar ao usuário.

O projeto foi desenvolvido em Python e testado no Google Colab.

## Estrutura sugerida do repositório

```text
SERS_GS2/
├── README.md
├── citizen_assist_ai.ipynb
├── requirements.txt
├── premissas_e_calculos.md
├── referencias.md
├── testes.md
├── ENTREGA.txt
└── .gitignore
```

O arquivo `citizen_assist_ai.ipynb` deve ser exportado do Google Colab usando **Arquivo > Fazer download > Fazer download do .ipynb** e adicionado a este repositório.

## Como executar

### Opção 1 — Google Colab (recomendado)

1. Abra o notebook `citizen_assist_ai.ipynb` no Google Colab.
2. Configure uma chave da API da OpenAI nos **Secrets** do Colab com o nome `OPENAI_API_KEY`.
3. Ative a permissão de acesso ao segredo para o notebook.
4. Execute as células na ordem.
5. Converse com o Citizen Assist AI na célula de interação.

O código deve recuperar a chave sem exibi-la:

```python
from google.colab import userdata
from openai import OpenAI

api_key = userdata.get("OPENAI_API_KEY")
client = OpenAI(api_key=api_key)
```

**Nunca publique sua chave de API no GitHub, no notebook ou em capturas de tela.**

### Opção 2 — Ambiente Python local

Instale as dependências:

```bash
pip install -r requirements.txt
```

Configure a variável de ambiente `OPENAI_API_KEY` e adapte a célula de inicialização do Colab para ler essa variável. O notebook preparado para Colab pode precisar de pequenos ajustes para execução local.

## Cenários de referência

Com as premissas documentadas, os resultados aproximados são:

| Cenário | Consumo mensal estimado | Custo mensal estimado |
|---|---:|---:|
| Chuveiro elétrico (15 min por pessoa, 5,5 kW) | 165 kWh | R$ 140,25 |
| Banho reduzido (10 min por pessoa, 3,5 kW) | 70 kWh | R$ 59,50 |
| Aquecimento solar (90% de cobertura térmica, com apoio elétrico) | 16,5 kWh | R$ 14,03 |
| Hábitos econômicos + solar | 7 kWh | R$ 5,95 |

Os resultados são cenários simplificados, não previsões garantidas. Consulte `premissas_e_calculos.md` para fórmulas, limitações e retorno estimado do investimento.

## Limitações

- A tarifa de R$ 0,85/kWh é uma premissa simplificada para simulação; a conta real pode incluir tributos, bandeiras, contribuição de iluminação pública e regras tarifárias específicas.
- A potência do chuveiro varia conforme modelo, tensão e posição de temperatura.
- A cobertura solar de 90% é hipotética e depende de clima, orientação, inclinação, sombreamento, dimensionamento, perdas e hábitos de consumo.
- Os custos de instalação usados para estimar retorno são cenários hipotéticos, não cotações de fornecedores.
- A estimativa de emissões usa um fator médio da eletricidade brasileira e não representa uma análise de ciclo de vida dos equipamentos.
- A recomendação final deve considerar a instalação hidráulica, espaço disponível, perfil de consumo, segurança e avaliação de profissional habilitado.

## Integrantes

Preencher os nomes completos e RMs em `ENTREGA.txt`.

## Entrega

- Repositório: https://github.com/lanaozeki08-jpg/SERS_GS2
- Vídeo de apresentação: inserir o link não listado em `ENTREGA.txt`.
- Registros dos testes: completar `testes.md` com perguntas realmente feitas e respostas observadas.
