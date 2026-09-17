---
layout: post
title: "Como Uso Inteligência Artificial no Meu Doutorado: Do Código Numérico à Pesquisa Científica"
date: 2026-09-17 20:30:00 -0300
author: Anderson Nunes
tags: [doutorado, inteligencia-artificial, pesquisa, engenharia-mecanica, produtividade]
---

Recentemente, meu amigo **Breno Dyego** me fez uma pergunta direta:

> *"Anderson, como é que você realmente usa inteligência artificial na rotina do seu doutorado? O que você faz no dia a dia?"*

A pergunta do Breno é excelente porque existe um abismo gigantesco entre o que o senso comum imagina sobre IA na pós-graduação e o que realmente significa fazer **pesquisa científica assistida por agentes inteligentes**.

Para a maioria das pessoas, "usar IA na pesquisa" ainda soa como abrir o ChatGPT no navegador, pedir para corrigir a gramática em inglês de um parágrafo ou pedir um resumo rápido de um artigo em PDF. Embora isso tenha sua utilidade, é apenas a ponta do iceberg.

No meu caso — fazendo doutorado em Engenharia Mecânica no **PPGEM/UFRN** (com foco em transferência radiativa computacional, modelos espectrais e acoplamento térmico, e cotutela na Alemanha) —, a pesquisa envolve física matemática pesada, equações diferenciais integro-diferenciais (como a Equação do Transporte Radiativo - RTE), estabilidade numérica e muito código científico. Não há espaço para alucinações.

A seguir, compartilho os pilares práticos de como estruturei esse **novo jeito de fazer doutorado**.

---

### 1. O Fim do "Código Solitário": IA como Pair Programmer Científico

Programação científica tem uma característica ingrata: implementar métodos numéricos (Monte Carlo, ordenadas discretas, volumes finitos) exige traduzir formulações analíticas densas em rotinas eficientes sem introduzir bugs sutis de discretização ou indexação.

Em vez de programar isolado no editor:
- **Implementação com Verificação Cruzada:** Ao desenvolver novos módulos do solver (em Python, C++ ou modernizando códigos legados em Fortran), utilizo a IA para escrever testes unitários matemáticos paralelos e checagens analíticas.
- **Cross-check Numérico:** Se estou testando uma convolução 3D ou um solver de espalhamento, peço ao modelo para derivar o caso limite analítico 1D correspondente ou montar um script comparativo de benchmark (por exemplo, comparando um algoritmo de Monte Carlo contra uma solução canônica da literatura).
- **Caça a Erros de Performance e Vetorização:** A IA me ajuda a identificar gargalos em loops aninhados do NumPy ou sugerir paralelizações em GPU/Numba, mantendo a equivalência matemática estrita.

O segredo aqui: **eu nunca peço código pronto sem um plano de validação**. A IA acelera a digitação e a exploração sintática; o teste físico de conservação de energia e resíduo define se o código presta.

---

### 2. O Ecossistema Conectado: Protocolo MCP e Ferramentas Reais

O divisor de águas entre um simples "chatbot" e um ambiente de trabalho produtivo é o **MCP (Model Context Protocol)** e a capacidade dos agentes executarem ferramentas locais.

Na minha máquina, os assistentes de IA não vivem numa aba isolada do navegador. Eles estão integrados diretamente à minha IDE e aos meus dados:

1. **Biblioteca Acadêmica via Zotero MCP:** Minha biblioteca do Zotero (com centenas de artigos anotados, metadados e tags) é consultável pelo agente. Quando preciso resgatar como determinado autor parametrizou o coeficiente de absorção espectral em 2018, o agente localiza o item exato na minha coleção local.
2. **Terminal e Scripts de Teste:** O agente pode rodar um script de validação, ler o terminal de saída, capturar uma mensagem de divergência de resíduo e propor ajustes diretamente no arquivo do solver.

---

### 3. Memória Persistente: Combatendo a Fadiga de Contexto

Um doutorado dura quatro anos. Ao longo desse tempo, você toma milhares de pequenas decisões metodológicas:
- *"Por que adotamos a quadratura de Gauss de 16 pontos em vez de 8?"*
- *"Qual foi a justificativa para descartar o modelo cinza na fase gasosa?"*
- *"Quais foram os parâmetros acordados com a supervisão para a cotutela?"*

Se você confiar apenas no cérebro ou em anotações espalhadas em cadernos e documentos avulsos, a perda de contexto é brutal.

Utilizo um sistema de **memória compartilhada local (`ai-memory`)**. Decisões duráveis, formulações aprovadas e parâmetros de projetos ficam registrados em páginas estruturadas. Quando volto a um problema meses depois, a IA tem acesso à trilha de raciocínio que já validamos, evitando que a pesquisa comece do zero a cada nova sessão.

---

### 4. Revisão Bibliográfica com Rastreabilidade Estrita

Pesquisa séria não aceita referências fictícias. Por isso, meu fluxo com IA para literatura segue três regras invioláveis:

- **Busca por APIs Acadêmicas:** Utilizo ferramentas integradas que consultam bases reais (OpenAlex, Crossref, arXiv, PubMed).
- **Inspeção dos PDFs Locais:** Uso ferramentas para extrair texto de papers específicos salvos no meu drive, perguntando sobre seções de metodologia exatas, e não pedindo palpites genéricos à IA.
- **Formulação de Perguntas e Hipóteses:** Onde a IA mais brilha não é em dar a resposta final, mas em atuar como debatedor socrático. Eu apresento um resultado físico inesperado e peço: *"Quais hipóteses concorrentes na literatura explicariam essa assimetria no perfil de atenuação?"*.

---

### 5. A Filosofia Fundamental: Ampliação, Não Substituição

A pergunta central que qualquer pós-graduando deve se fazer é: **a IA está tirando o atrito da mecânica ou está substituindo o pensamento?**

- Se você usa IA para terceirizar a compreensão, o doutorado perde o sentido. Você se torna um mero operador que não domina o próprio tema na banca de defesa.
- Mas se você usa IA para **eliminar o atrito burocrático e operacional** — montagem de boilerplate, checagem cruzada de scripts, busca estruturada em referências, automação de gráficos e deploys —, você ganha algo inestimável: **tempo de qualidade para pensar a física do problema**.

Para mim, o doutorado não se tornou mais fácil; ele se tornou **muito mais profundo**. Com o ferramental certo, consigo rodar mais experimentos, testar mais hipóteses e refinar mais modelos em uma semana do que conseguiria em um mês de rotina puramente manual.

---

### Dica para o Breno (e para quem quer começar hoje)

Se você quer começar a aplicar isso na sua pós-graduação sem se perder:

1. **Traga a IA para perto dos seus arquivos:** Pare de copiar e colar no ChatGPT web. Use extensões na sua IDE (como GitHub Copilot, Gemini CLI, Antigravity ou Claude Code) para que a IA enxergue seus scripts e dados.
2. **Integre sua literatura:** Conecte sua ferramenta de IA ao seu Zotero ou pasta de artigos.
3. **Mantenha o rigor:** Não aceite uma linha de código ou equação sem entender sua derivação. Use a IA para explicar o porquê de cada passo, não apenas para cuspir o resultado.

Esse é o novo jeito de fazer ciência. E a melhor parte é que estamos apenas no começo.
