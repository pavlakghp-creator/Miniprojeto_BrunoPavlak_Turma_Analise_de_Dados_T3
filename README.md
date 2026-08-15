## 📌 Visão Geral do Projeto



Este projeto consiste no desenvolvimento de um pipeline completo de Análise Exploratória de Dados (AED) aplicado à base de dados `Base Varejo`. O objetivo principal foi realizar o processo de extração, limpeza, conversão de tipos de dados e tratamento de inconsistências, gerando estatísticas descritivas e agrupamentos estratégicos para apoiar tomadas de decisão comercial.

---



## 🧠 Reflexão Teórica: Processo de ETL e Qualidade de Dados

A qualidade dos dados foi minha premissa fundamental para a construção deste Pipeline. Durante a etapa de  **Transformação (T do ETL)** , a decisão sobre a forma de tratamento de lacunas e divergências determinou na possibilidade buscar informações mais precisas para minhas análises:

1. **Leitura Estruturada:** A leitura direta utilizando `pd.read_csv()` permitiu o carregamento vetorizado e otimizado da base `Base Varejo`. A especificação correta do separador (`;`) e da codificação (`utf-8-sig`) evitou erros de separação de colunas e eliminou caracteres ocultos do cabeçalho logo na entrada dos dados.
2. **Tratamento de Nulos e Inconsistências (#N/D):** A substituição de células vazias e erros de planilha (`#N/D`) por `NaN` e o preenchimento condicional de categorias ausentes com `"Sem Categoria"` garantiram a integridade das agregações de vendas sem a perda arbitrária de registros financeiros.
3. **Eliminação de duplicatas:** A eliminação de duplicatas trouxe uma maior segurança as informações levantadas, mitigando possíveis levantamento incorretos por problemas sistêmicos do varejo.
4. **Conversão de Tipos e Temporalidade:** A tipagem rigorosa (de strings para inteiros/floats e objetos para `datetime`) permitiram cálculos estatísticos precisos e possibilitaram a filtragem cronológica do comportamento do varejo.

## 💡 Principais Insights da Análise (Conclusões)

1. **Dominância do Segmento Sem Filhos (`CL_FHL = 0`):** Clientes sem filhos concentram mais de 52% do volume total de itens comprados na rede (~385 mil itens), superando amplamente os demais grupos familiares.
2. **Estabilidade de Vendas em Famílias Médias:** Clientes com 1 a 3 filhos apresentam volume de consumo constante (~90 mil a 94 mil itens cada grupo), havendo queda expressiva apenas no grupo com 4 filhos (~71 mil itens).
3. **Hierarquia Invariável da Cesta de Compras:** Em todos os perfis, a categoria de **Alimentos** lidera o volume de vendas (~52%), seguida por **Higiene** (~18%) e **Limpeza** (~17%).
4. **Resolução de Inconsistências de Planilha:** Foram tratados registros nulos e códigos de busca com falha (`#N/D`), permitindo mapear 100% da base sem distorcer o cálculo do ticket médio e agrupamentos por gênero e classe social.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.12.10
* **Bibliotecas:** `pandas`, `numpy`, `datetime`
* **IDE:** VSCode
* **Versionamento:** Git e GitHub
