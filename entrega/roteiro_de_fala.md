# Roteiro de fala – Saúde Prime (20 a 25 min)

Total de falas: **2329 palavras**. Em ritmo calmo (~110 palavras/min) dá ~21 min de fala; em ritmo normal (~130/min), ~18 min. Somando trocas de slide, passagem entre apresentadores e pausas, a apresentação fica entre **20 e 24 minutos**.

Divisão: Marcelo: 769 palavras (~6.4 min) · Matheus: 754 palavras (~6.3 min) · Milan: 806 palavras (~6.7 min)

**Dicas de tempo:** ensaiem com cronômetro. Se no fim do slide 9 já tiverem passado 12 minutos, encurtem a explicação do diagrama (slide 10) e do Terraform (slide 12). Nunca cortem os slides 14 a 16 (custos e retorno): foram o ponto que o professor pediu para reforçar.

| # | Slide | Quem | Tempo |
|---|---|---|---|
| 1 | Plano Estratégico de Informatização | Marcelo | ~40 s |
| 2 | O que vamos apresentar | Marcelo | ~30 s |
| 3 | Uma operadora de grande porte que vive de dados | Marcelo | ~1 min |
| 4 | Quatro processos sustentam a operação | Marcelo | ~1 min 15 s |
| 5 | Como os dados circulam hoje | Marcelo | ~1 min 30 s |
| 6 | Quatro gargalos travam a gestão | Marcelo | ~1 min 30 s |
| 7 | Dados de saúde são dados sensíveis na LGPD, e hoje circulam em planilhas sem controle de acesso. | Marcelo | ~1 min |
| 8 | Arquitetura Medalhão: refino em três camadas | Matheus | ~1 min 30 s |
| 9 | Dados organizados abrem dois caminhos | Matheus | ~1 min |
| 10 | Arquitetura proposta na nuvem Microsoft Azure | Matheus | ~2 min |
| 11 | Segurança e ética desde o projeto | Matheus | ~1 min 30 s |
| 12 | Infraestrutura como Código com Terraform | Matheus | ~50 s |
| 13 | De licença por pessoa para capacidade compartilhada | Milan | ~1 min 15 s |
| 14 | Quanto custa: estimativa mensal | Milan | ~1 min 30 s |
| 15 | O retorno chega em três ondas | Milan | ~2 min |
| 16 | Recuperar metade das horas manuais já paga a diferença | Milan | ~1 min |
| 17 | Dados governados deixam de ser um risco e passam a ser um ativo estratégico | Milan | ~1 min |
| 18 | Obrigado! | Milan | ~30 s, depois perguntas |

## 1. Plano Estratégico de Informatização
*Marcelo · ~40 s*

Bom dia a todos. Eu sou o Marcelo e, junto com o Matheus e o Milan, vamos apresentar o Plano Estratégico de Informatização da Saúde Prime Araraquara, uma operadora de convênio médico. O tema do nosso trabalho é uma plataforma de ingestão e visualização de dados. Nos próximos minutos vamos mostrar o diagnóstico da empresa, a arquitetura em nuvem que propomos e por que esse investimento vale a pena.

## 2. O que vamos apresentar
*Marcelo · ~30 s*

A apresentação tem três partes. Eu começo apresentando a empresa e o diagnóstico da situação atual. Depois o Matheus explica a fundamentação e a arquitetura em nuvem que propomos. Por fim, o Milan mostra os custos, por que vale a pena investir mais e quando esse investimento retorna, e fecha com a conclusão.

## 3. Uma operadora de grande porte que vive de dados
*Marcelo · ~1 min*

A Saúde Prime Araraquara é uma empresa fictícia, mas construída a partir de operações reais de operadoras de planos de saúde de grande porte. Ela atua na saúde suplementar, ou seja, convênio médico. São cerca de 1.200 funcionários diretos e mais de 2.000 médicos e clínicas credenciados na região. A empresa vende planos empresariais e familiares, administra a rede credenciada, faz auditoria médica, libera exames e cirurgias e acompanha pacientes crônicos. Na prática, isso significa milhares de guias, contas e cadastros novos todos os dias. O ponto importante aqui é que todas essas atividades geram e dependem de dados o tempo todo. Por isso, a forma como a empresa trata a informação impacta diretamente o negócio.

## 4. Quatro processos sustentam a operação
*Marcelo · ~1 min 15 s*

A operação se apoia em quatro processos principais. Primeiro, Contas e Despesas: fechar as contas que chegam dos hospitais, calcular o que precisa ser pago e controlar quanto a empresa realmente gasta. Segundo, a Liberação de Guias: receber o pedido médico, verificar se o paciente ainda está em carência e liberar exames, cirurgias ou internações. Terceiro, o Controle de Clientes: quem entra no plano, quem cancela, portabilidade e cobrança de mensalidades atrasadas. E quarto, o Pagamento da Rede Credenciada, que é o repasse para médicos, laboratórios e hospitais. Qualquer erro ou atraso nesses processos vira prejuízo financeiro ou um atendimento negado indevidamente. Por isso esses processos são o foco da nossa proposta: são eles que mais sofrem com a falta de dados confiáveis.

## 5. Como os dados circulam hoje
*Marcelo · ~1 min 30 s*

Agora o diagnóstico. A Saúde Prime recebe diariamente um volume enorme de dados de três sistemas: o ERP hospitalar, o portal de autorização de guias e o CRM de atendimento. O problema está no caminho que esse dado percorre. Não existe um processo automatizado e seguro de extração. Os analistas exportam arquivos CSV manualmente e montam planilhas. Depois, cada pessoa com licença do Power BI publica o seu próprio relatório. Hoje são cerca de 200 licenças Premium Per User. No fim da linha está a diretoria, que recebe números diferentes vindos de áreas diferentes. Ou seja: a empresa tem muita informação, mas a trata de forma ultrapassada, lenta e com alto risco de erro humano. Além do tempo perdido, cada cópia de planilha é mais um arquivo com dados de pacientes circulando sem controle, e isso vai aparecer de novo quando falarmos de LGPD.

## 6. Quatro gargalos travam a gestão
*Marcelo · ~1 min 30 s*

Desse cenário saem quatro gargalos. Primeiro, o trabalho manual: a equipe de dados e os analistas de negócio gastam horas exportando planilhas, o que gera lentidão e erro. Segundo, a falta de governança: como todas as 200 licenças são iguais, não existe controle de quem cria painel e de quem deveria apenas visualizar. Isso espalha relatórios não homologados. Terceiro, não existe uma estrutura de dados: o dado chega bruto, sem tratamento, os relatórios ficam confusos e a diretoria desconfia deles. Sem essa base, também não dá para usar Inteligência Artificial. E quarto, o conflito de informações: a área Médica e o Comercial montam o mesmo indicador de jeitos diferentes, e as reuniões viram uma discussão sobre qual número está certo, em vez de decisões. E esses problemas se reforçam: sem estrutura de dados não há governança, e sem governança os números não batem.

## 7. Dados de saúde são dados sensíveis na LGPD, e hoje circulam em planilhas sem controle de acesso.
*Marcelo · ~1 min*

E o risco mais grave de todos é jurídico. A LGPD classifica informações médicas, como histórico de exames, diagnósticos e tratamentos, como dados sensíveis, que exigem o mais alto nível de proteção. No cenário atual, planilhas com nomes, CPFs e dados de saúde circulam entre áreas sem controle de quem acessa. A lei prevê multa de até 2% do faturamento, limitada a 50 milhões de reais por infração, e o dano à reputação de uma operadora de saúde pode ser ainda maior. Ou seja, além de um problema de eficiência, a desorganização dos dados é um risco jurídico que precisa ser tratado com prioridade. Com isso eu passo para o Matheus, que vai apresentar como a nossa proposta resolve esses problemas.

## 8. Arquitetura Medalhão: refino em três camadas
*Matheus · ~1 min 30 s*

Obrigado, Marcelo. A base técnica da nossa proposta é a Arquitetura Medalhão, um padrão de mercado em engenharia de dados. A ideia é organizar o caos: dados vindos de hospital têm erro de digitação, formato incorreto e informação duplicada. Então o tratamento é dividido em três camadas dentro do Data Lake. A camada Bronze recebe o dado bruto, exatamente como saiu do ERP e do CRM, e guarda esse histórico intocado para auditoria ou para reprocessar algo. Na camada Prata o dado é limpo e padronizado: datas no mesmo formato, cadastros duplicados de pacientes removidos, e é também aqui que mascaramos CPF e nome. Por fim, a camada Ouro organiza os dados em modelos de negócio prontos para consumo. Ela é a fonte única da verdade: todo painel da empresa vai beber dessa mesma fonte. Outra vantagem: se uma regra de negócio mudar, basta reprocessar a partir da Bronze, sem extrair tudo de novo dos sistemas de origem.

## 9. Dados organizados abrem dois caminhos
*Matheus · ~1 min*

Com os dados organizados, abrimos dois caminhos. O primeiro é a visualização: de nada adianta ter o dado mais limpo do mundo se o gestor precisa ler milhares de linhas para entender o que está acontecendo. Com painéis interativos, a diretoria enxerga rapidamente uma tendência, por exemplo um pico incomum de internações em uma região, e decide com agilidade. O Fabric ainda tem o Copilot, que responde perguntas em linguagem natural. O segundo caminho é a Inteligência Artificial. O Databricks e o Fabric já vêm com ferramentas de Machine Learning e agentes de IA. Com a base pronta, a empresa poderá prever a ocupação de leitos e identificar riscos de fraude em guias médicas. Ou seja, a mesma base de dados serve tanto para a gestão do dia a dia quanto para a inovação.

## 10. Arquitetura proposta na nuvem Microsoft Azure
*Matheus · ~2 min*

Este é o desenho da arquitetura completa. Vou seguir o caminho do dado da esquerda para a direita. À esquerda estão as fontes: ERP hospitalar, portal de guias e CRM. Os dados entram automaticamente no Azure, na região Brazil South, em São Paulo, dentro de um Resource Group que agrupa todos os recursos e facilita o controle de custos. Tudo roda dentro de uma rede privada, a VNet, sem passar pela internet pública. No centro está o Azure Databricks, o motor de processamento: ele faz a ingestão e executa as transformações entre as camadas. Logo abaixo está o Data Lake, uma Storage Account com as camadas Bronze, Prata e Ouro. O Key Vault guarda senhas e certificados, e os Private Endpoints garantem que o acesso aos serviços seja só pela rede privada. A camada Ouro alimenta o Microsoft Fabric F64, onde uma equipe pequena publica os painéis e o restante da empresa só consome, cada um com acesso de acordo com o seu cargo. No canto superior direito está a próxima etapa, a IA. E na base, o Terraform, que cria e versiona toda essa infraestrutura. Reparem que nenhum relatório lê direto do ERP ou do CRM: tudo passa pelo Data Lake e chega ao Fabric já tratado. É isso que garante que todas as áreas vejam o mesmo número.

## 11. Segurança e ética desde o projeto
*Matheus · ~1 min 30 s*

Como lidamos com dados de saúde, a segurança foi pensada desde o início do projeto, com quatro medidas. Primeiro, residência de dados: todos os recursos do Azure e do Fabric ficam na região Brazil South, em São Paulo, então os dados dos pacientes não saem do território nacional. Segundo, rede fechada: a VNet e os Private Endpoints bloqueiam qualquer acesso externo, e o Key Vault centraliza senhas e certificados, para que nenhuma credencial fique espalhada em código ou planilha. Terceiro, anonimização: na camada Prata, nome e CPF são mascarados, então as áreas gerenciais e comerciais conseguem gerar estatísticas de saúde sem violar a privacidade de ninguém. E quarto, controle de acesso por cargo: apenas médicos e auditores estritamente autorizados enxergam os dados identificados. Assim, a mesma arquitetura que resolve o problema de eficiência também resolve o risco jurídico que o Marcelo mostrou.

## 12. Infraestrutura como Código com Terraform
*Matheus · ~50 s*

Por fim, toda essa infraestrutura será criada com Terraform, que é Infraestrutura como Código. Em vez de criar os recursos clicando manualmente no portal do Azure, cada recurso é descrito em código, como neste exemplo do Resource Group e do Key Vault, já na região Brazil South. Isso traz três vantagens: o ambiente fica versionado e documentado, evitamos falhas de segurança causadas por configuração manual errada e, em caso de desastre, conseguimos recriar o ambiente a partir do código. Também fica fácil criar um ambiente de testes idêntico ao de produção. Agora o Milan vai falar sobre custos e retorno.

## 13. De licença por pessoa para capacidade compartilhada
*Milan · ~1 min 15 s*

Obrigado, Matheus. O maior gargalo de gestão hoje é o licenciamento. A Saúde Prime paga cerca de 200 licenças Premium Per User. O problema é duplo. Primeiro, governança: todo mundo pode publicar, então não existe separação entre quem desenvolve o relatório e quem deveria apenas consumir. Segundo, eficiência: o PPU é só visualização. A empresa paga caro e continua sem estrutura para Medalhão ou IA. Além disso, cada novo leitor exige uma nova licença. A proposta é migrar para a capacidade F64 do Microsoft Fabric com o Databricks no backend. Nesse modelo, só uma equipe de cerca de 20 desenvolvedores tem licença Pro para publicar, e os demais usuários, inclusive novos, consomem os relatórios sem licença individual. Isso muda a lógica: hoje, ampliar o acesso aos dados significa pagar mais; na proposta, ampliar o acesso não aumenta o custo de licenças.

## 14. Quanto custa: estimativa mensal
*Milan · ~1 min 30 s*

Vamos aos números. Hoje são 200 licenças PPU a 24 dólares por mês, porque a Microsoft reajustou esse preço em abril de 2025. Isso dá cerca de 4.800 dólares mensais. Na proposta, precisamos de 20 licenças Pro para os desenvolvedores, cerca de 280 dólares, mais a capacidade F64 com reserva anual, por volta de 5 mil dólares, mais o consumo do Databricks, do armazenamento e da rede, que estimamos entre 1.500 e 2.500 dólares. O total fica entre 6.800 e 7.800 dólares por mês. Ou seja, sim: a proposta custa mais, algo entre 2 e 3 mil dólares por mês. A pergunta central então é: por que pagar essa diferença e quando ela retorna? É o que mostro agora. Lembrando que são estimativas com preços de lista, e os valores exatos para a região Brazil South serão refinados na segunda parte do trabalho.

## 15. O retorno chega em três ondas
*Milan · ~2 min*

O retorno desse investimento chega em três ondas. No curto prazo, de zero a seis meses, o retorno não é receita, é risco e custo evitados. Com anonimização, rede privada e controle de acesso, a exposição a multas da LGPD cai bastante. E tem um custo evitado bem concreto: se a empresa quisesse abrir os painéis para mais 300 médicos credenciados no modelo atual, teria que comprar 300 licenças PPU, cerca de 7.200 dólares por mês. Na capacidade F64, esses usuários entram como leitores sem custo adicional. No médio prazo, de seis a dezoito meses, o retorno vem da produtividade: os analistas param de montar planilhas e as reuniões deixam de discutir qual número está certo. É nessa fase que o investimento se paga, e eu mostro a conta no próximo slide. No longo prazo, depois de um ano e meio, vem o maior retorno: com dados limpos e históricos, a IA pode auditar contas e guias automaticamente para detectar fraudes e desperdícios, e prever a ocupação de leitos. Reparem que uma onda sustenta a outra: a redução de risco protege a empresa enquanto a plataforma é implantada, a produtividade cobre o custo mensal e a IA traz o maior ganho financeiro.

## 16. Recuperar metade das horas manuais já paga a diferença
*Milan · ~1 min*

Aqui está a conta do médio prazo, com premissas conservadoras. Se 15 analistas gastam cerca de 12 horas por semana exportando e consolidando planilhas, são cerca de 720 horas por mês. A um custo de 50 reais por hora, isso dá 36 mil reais por mês, aproximadamente 6.500 dólares. Basta recuperar metade dessas horas, cerca de 3.250 dólares, para cobrir a diferença de 2 a 3 mil dólares da nova plataforma. Por isso estimamos que o investimento se paga entre 12 e 18 meses, já contando o tempo de implantação. E no longo prazo o potencial é muito maior: segundo o IESS, fraudes e desperdícios consumiram entre 30 e 34 bilhões de reais da saúde suplementar em 2022. Reduzir uma fração mínima disso já supera com folga o custo anual da plataforma. E essas contas ainda não incluem o ganho de decisões mais rápidas na diretoria, que é difícil de medir, mas é real.

## 17. Dados governados deixam de ser um risco e passam a ser um ativo estratégico
*Milan · ~1 min*

Para concluir: o diagnóstico mostrou uma operadora que depende de dados, mas que ainda os trata de forma manual, sem governança e com risco real à LGPD. A nossa proposta é uma arquitetura Medalhão processada no Databricks, com visualização no Fabric F64, tudo em rede privada, com os dados no Brasil e criado via Terraform. Sim, ela custa mais por mês, mas reduz riscos logo de início, se paga no médio prazo com produtividade e gera o maior valor no longo prazo com IA. Como dizem Laudon e Laudon, sistemas de informação geram valor quando estão alinhados ao negócio, e é isso que essa proposta faz: transforma os dados de um passivo de risco em um ativo estratégico. Na segunda parte do trabalho vamos detalhar o cronograma, refinar os custos e definir os indicadores para acompanhar esse retorno.

## 18. Obrigado!
*Milan · ~30 s, depois perguntas*

Essa foi a nossa proposta. As principais referências estão aqui, e a lista completa está no documento do trabalho. Muito obrigado pela atenção. Ficamos à disposição para perguntas.
