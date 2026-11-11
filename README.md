# Citizen Assist AI — Energia Sustentável

## Sobre o projeto

O Citizen Assist AI é um chatbot que ajuda famílias a compreender o consumo de energia relacionado ao aquecimento de água e banhos e a comparar alternativas para reduzir gastos e impactos ambientais.

O estudo de caso compara:

1. Chuveiro elétrico convencional;
2. Redução do tempo de banho e uso de potência econômica;
3. Aquecimento solar térmico de água, mantendo apoio elétrico para a parcela de demanda não atendida pelo sol.

O público-alvo é uma família residencial de referência com quatro moradores, em São Paulo (SP), de classe média. 

Este projeto é uma simulação educativa. Os valores são estimativas baseadas nas premissas descritas em `premissas_e_calculos.md`, e não substituem uma avaliação técnica da residência ou um orçamento de instalação.

## Objetivos

- Estimar o consumo mensal de energia do chuveiro elétrico;
- Traduzir o consumo em custo financeiro;
- Comparar cenários de economia por mudança de hábitos e aquecimento solar térmico;
- Estimar a redução de emissões associadas à eletricidade consumida;
- Explicar resultados em linguagem simples por meio de uma conversa com IA.

## Tecnologias e bibliotecas

- Python: linguagem de programação.
- OpenAI API: conexão com o modelo de IA.
- GPT-4o-mini: modelo utilizado para interpretar perguntas e elaborar respostas.
- Google Colab: ambiente de desenvolvimento.
- Biblioteca openai: comunicação com a API da OpenAI.
- json: tratamento dos argumentos e resultados das ferramentas.
- getpass / Google Colab Secrets: proteção e gerenciamento da chave de API.

## Premissas da simulação

- Número de moradores: 4
- Banhos por pessoa: 1 por dia
- Duração convencional do banho: 15 minutos
- Potência convencional do chuveiro: 5,5 kW
- Duração econômica do banho: 10 minutos
- Potência no cenário econômico: 3,5 kW
- Tarifa de energia: R$ 0,85/kWh
- Dias no mês: 30 dias
- Cobertura hipotética do aquecimento solar: 90%
- Investimento de referência: R$ 5.000

Os valores são premissas simplificadas, não representam necessariamnente o consumo de uma residência real nem uma cotação comercial.

## Comparação dos cenários: 

| Cenário | Consumo mensal estimado | Custo mensal estimado |
|---|---:|---:|
| Chuveiro elétrico (15 min por pessoa, 5,5 kW) | 165 kWh | R$ 140,25 |
| Banho reduzido (10 min por pessoa, 3,5 kW) | 70 kWh | R$ 59,50 |
| Aquecimento solar (90% de cobertura térmica, com apoio elétrico) | 16,5 kWh | R$ 14,03 |
| Hábitos econômicos + solar | 7 kWh | R$ 5,95 |

## Bibliotecas e dependências: 

openai: integração com os modelos de inteligência artificial da OpenAI.
As bibliotecas json e getpass fazem parte da biblioteca padrão do Python. No Google Colab, também é utilizado o recurso google.colab.userdata para acessar a chave de API armazenada nos Secrets.

Para instalar a principal dependência:

!pip install openai

## Como o chatbot funciona

1. O usuário envia uma pergunta.
2. O modelo interpreta a mensagem.
3. Quando necessário, chama a ferramenta de cálculo.
4. O Python realiza os cálculos.
5. O modelo utiliza os resultados para responder.

## Estrutura do repositório

```text
SERS_GS2/
├── README.md
├── SERS.GS2.ipynb
├── testes.pdf
```

## Como executar

1. Abra o notebook `citizen_assist_ai.ipynb` no Google Colab.
2. Configure uma chave da API da OpenAI nos Secrets do Colab com o nome `OPENAI_API_KEY`.
3. Ative a permissão de acesso ao segredo para o notebook.
4. Execute as células na ordem.
5. Converse com o Citizen Assist AI na célula de interação.
6. !pip install openai

## Limitações

- A tarifa de R$ 0,85/kWh é uma premissa simplificada para simulação; a conta real pode incluir tributos, bandeiras, contribuição de iluminação pública e regras tarifárias específicas.
- A potência do chuveiro varia conforme modelo, tensão e posição de temperatura.
- A cobertura solar de 90% é hipotética e depende de clima, orientação, inclinação, sombreamento, dimensionamento, perdas e hábitos de consumo.
- Os custos de instalação usados para estimar retorno são cenários hipotéticos, não cotações de fornecedores.
- A estimativa de emissões usa um fator médio da eletricidade brasileira e não representa uma análise de ciclo de vida dos equipamentos.
- A recomendação final deve considerar a instalação hidráulica, espaço disponível, perfil de consumo, segurança e avaliação de profissional habilitado.

## Referências:

- Empresa de Pesquisa Energética (EPE) — Atlas da Eficiência Energética Brasil 2024.
- Empresa de Pesquisa Energética (EPE) — Balanço Energético Nacional 2026.
- Enel São Paulo — Tarifas de energia elétrica.
- INMETRO — Equipamentos de aquecimento solar de água.
- https://www.epe.gov.br/pt/publicacoes-dados-abertos/publicacoes/atlas-de-eficiencia-energetica-brasil-2024
- https://www.epe.gov.br/sites-pt/publicacoes-dados-abertos/publicacoes/PublicacoesArquivos/publicacao-975/topico-847/BEN_S%C3%ADntese_2026_PT.pdf
- https://www.enel.com.br/pt-saopaulo/Para_Voce/tarifa-de-energia-eletrica.html
- https://www.gov.br/inmetro/pt-br/assuntos/regulamentacao/avaliacao-da-conformidade/programa-brasileiro-de-etiquetagem/tabelas-de-eficiencia-energetica/equipamentos-de-aquecimento-solar-de-agua

## Integrantes
- Lana Namie Kano Ozeki - RM 569795
- Luan de Araujo Carneiro - RM 573691
- Pedro Ribeiro Lopes - RM 570083
