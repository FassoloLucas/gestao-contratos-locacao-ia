# Módulos

Cada área vê só os módulos liberados para ela; o administrador controla esse acesso numa tela própria. Abaixo, as telas de cada módulo e o que entregam.

## Contratos

Contratos de aluguel das lojas, da importação do PDF ao reajuste, à renovação e ao pagamento.

- **Dashboard:** contratos com busca por locador, empresa e filial, filtros de vencimento e indicadores de reajuste pelo índice escolhido (IGP-M, IPCA, INPC ou IGP-DI). Ficha com PDF, contatos, término e histórico.
- **Cadastrar filiais:** filiais por empresa do grupo; a exclusão é recusada se houver contrato ligado.
- **Importar contrato:** a IA lê o PDF (locador, valores, datas, índice, vencimento) e cria o cadastro com o evento de criação no histórico. Trata renovação, que herda o histórico do contrato anterior, e troca do PDF.
- **Calcular reajustes:** correção do aluguel pelo índice acumulado de 12 meses, com o passo a passo de cada aniversário. Simular não grava nada.
- **Extrato de movimentação:** linha do tempo de cada contrato, agrupada por filial ou ano, com eventos manuais e exclusão justificada. A data da renovatória é calculada dez meses antes do fim.
- **Títulos de aluguel:** busca no ERP os títulos de aluguel pagos com IR retido, por período e pessoa, e vincula os pagamentos ao contrato.

## Comercial

Acordos comerciais com fornecedores, que geram títulos a receber, e a inadimplência desses acordos.

- **Dashboard:** evolução mensal, formas de recebimento, maiores fornecedores e compensações, por período, fornecedor, comprador e situação. Exporta PDF.
- **Consultar acordos:** acordos em aberto ou quitados, por emissão ou vencimento, com o detalhe de cada título.
- **Análises com IA:** fornecedores, compradores, sazonalidade e conformidade das baixas, em relatório de texto com pontos de atenção.
- **Inadimplência:** títulos em aberto por comprador e fornecedor, em tabela ou visão dinâmica por ano, com justificativa por título e exclusão do relatório sem alterar o ERP. A relação fornecedor → comprador pode ser carregada por CSV.

## Financeiro

Rotinas que cruzam dados do ERP com arquivos externos.

- **Tarifas mensais:** lançamentos das contas de tarifas por período, conta e filial, com as 10 maiores contas e filiais, Excel e PDF.
- **Análises IA:** compara a movimentação contábil de dois meses e destaca variações acima de 10%.
- **Conciliação iFood:** recebe o financeiro do sistema, o extrato do iFood e as contestações, e cruza pedido a pedido o líquido de cada lado. Gera um ZIP com planilhas por fato gerador e por filial.
- **Fluxo de caixa:** movimento das contas de fundo fixo por loja, operação e período, com evolução diária e maiores operações.
- **Itens cancelados:** cancelamentos de itens no PDV por loja, caixa, operador e fiscal, com rankings e horários.

## Contabilidade

O módulo mais extenso: rotinas do dia a dia, relatórios de resultado e os controles de arrendamento e depreciação.

- **Consumo:** notas de consumo por filial e CGO, com Excel geral e por CGO.
- **Agenda geral:** obrigações mensais, trimestrais, anuais ou únicas, com regras de vencimento (dia fixo, dia útil anterior, último dia útil, enésimo dia útil), conclusão e reabertura por período.
- **Notas de orçamento:** notas de despesa com fornecedor, conta, natureza, vencimento e retenções.
- **Livro razão:** por conta do ERP ou pelo referencial da Receita Federal, com resumo por conta, páginas de 200 lançamentos e PDF de até 200 mil lançamentos.
- **Empresas e calculadora de tributos:** cadastro fiscal de cada empresa (regime, atividade, conta de receita) e cálculo de PIS/COFINS e IRPJ/CSLL no Lucro Presumido, DAS do Simples e tributos do Lucro Real, em simulação ou gravação, individual ou em lote.

### DRE (sete páginas)

- **Dashboard:** seis indicadores, a escada "para onde vai cada R$ 100 de receita líquida", evolução de receita e margens, ranking por empresa e detalhamento até a conta. Mês a mês ou acumulado, com comparativo. Exporta PDF e blocos em PNG para apresentações.
- **Análise de despesas:** despesas por fornecedor, grupo, conta, mês e filial em três anos, com quatro fontes de documento (livro fiscal, notas de despesa e serviço, financeiro e folha) e o que a DRE lançou sem documento.
- **Consolidado:** balancete comparativo entre dois períodos.
- **DRE:** 24 meses, com CMV contábil ou gerencial.
- **DRE por loja:** despesas mensais por loja no modelo da DRE do ERP, visão por loja ou geral, observações por loja, mês e linha, contas fora do modelo e Excel no layout da planilha que ela substituiu.
- **DRE com CMV contábil** e **cadastro do CMV gerencial** por competência e empresa.

### Arrendamento (CPC 06)

Substitui a planilha de arrendamento. Tudo é calculado no servidor; a tela não recalcula valores contábeis.

- **Contratos:** saldos na competência e ficha com cronograma mês a mês (curto e longo prazo, juros a apropriar, custo e amortização), lançamentos por ano e pendências.
- **Eventos:** reajuste, renovação ou encerramento, com prévia antes de gravar (antes × depois, lançamentos e 12 meses de comparação). Evento que atinge competência fechada é bloqueado.
- **Fechamento mensal:** situação da competência, avisos e totais por modelo, conta, filial e centro de custo. Competências fecham em sequência e só a última reabre.
- **Conciliação:** compara o módulo com o razão do ERP no consolidado, por filial e parcelas × pagamentos por locador.
- **Pendências** e **Parâmetros** (taxas, decisões e plano de contas do módulo).

### Controle de depreciação

Substitui a planilha de imobilizado.

- **Bens:** cadastro por grupo, situação, filial e ano de ativação, com trilha de quem alterou e quando.
- **Novos bens:** busca no ERP os débitos nas contas de ativo do mês e as notas que seguem no imobilizado a classificar; o usuário confirma ou ignora cada candidato. Créditos aparecem como alerta de possível baixa.
- **Competências:** calcula o mês, mostra o resumo por grupo e por bem, concilia com o saldo do ERP e gera o arquivo de lançamento no layout de importação do ERP.
- **Grupos:** contas de ativo, depreciação acumulada e despesa, vida útil padrão e ajuste inicial da conciliação.

## Fiscal

Conferência das notas de entrada, apoio às apurações e consultas do livro fiscal e do SPED.

- **Conferência XML:** compara o XML de cada NF-e de entrada com o lançamento no ERP, no cabeçalho (total, frete, seguro, emissão) e item a item (valor, quantidade, preço, ICMS, ST, IPI, PIS/COFINS, CFOP e NCM). Os XMLs vêm de um ZIP do usuário ou do portal NDD. Planilha com cinco abas: Resumo, Divergências, Notas, Itens e Notas corretas.
- **Painel NFe:** consulta as notas no NDD por período e CNPJ, com download do XML por nota ou em lote.
- **F100:** registro F100 da EFD-Contribuições, separando créditos normais do adicional da LC 224.
- **FCP:** base, fundo e saldo por filial, nas entradas e nas saídas, com Excel.
- **DIFAL:** diferencial de alíquota nas entradas para ativo imobilizado e uso e consumo, com DIFAL e FCP por nota e por item.
- **Emissões canceladas:** confronta as NF-e canceladas e inutilizadas na SEFAZ com o livro fiscal, na emissão e na entrada da filial de destino, para todas as filiais de uma vez.
- **Fornecedores:** documentos do livro fiscal pelos CGOs escolhidos, em visão analítica (por item) ou sintética (por nota).
- **Extrator XML:** lê XML, ZIP ou uma pasta inteira no navegador (NF-e, CT-e, NFS-e e eventos) e gera Excel sem enviar os arquivos ao servidor.
- **Resumo SPED:** lê o .txt da EFD ICMS/IPI de uma ou várias filiais no navegador e soma os registros analíticos por CFOP, CST e alíquota, com abertura de cada linha nas notas.

### Situações da conferência

- **Divergência:** valor, quantidade, imposto, CFOP ou NCM diferente, acima da tolerância.
- **Nota correta:** cabeçalho sem achados e todos os itens conferidos.
- **Sem XML:** nota lançada sem XML encontrado.
- **Dados incompletos:** falta dado essencial para comparar; não conta como divergência.
- **Dados XML indisponíveis:** item fora da importação de XML do ERP; comparação suspensa.
- **Transferência interna:** nota entre empresas do grupo sem documento disponível.
- **Payload NDD:** transferência conferida pelo arquivo de integração enviado ao portal.

## Orçamento

- **Orçamento anual:** aprovado × consumido por setor, com ranking, detalhe por mês, conta e loja, e projeção do ano a partir dos meses fechados.
- **Definir orçamento:** valor anual por setor, com opção de copiar o ano anterior.
- **Gerenciar budget:** liga cada conta analítica de despesa a um setor, por ano, e lista as contas fora do budget.
- **Links por setor:** link de consulta sem login para cada setor, com troca de ano e revogação.

## Administração

- **Usuários e acessos:** cadastro com e-mail corporativo, login Google ou senha inicial, módulos liberados, bloqueio e exclusão.
- **Chave da IA:** cadastro da chave, modelo e instruções; a tela mostra só se a chave existe, nunca o valor.
- **Monitor:** quem está online, o que está em processamento e as operações dos últimos 7 dias, sem guardar os filtros usados.

## Assistente de IA

Disponível em todas as telas. Recebe o contexto resumido da tela aberta (filtros, totais, linhas visíveis), responde só sobre módulos liberados ao usuário, não consulta o ERP por conta própria e diferencia uma divergência fiscal de uma conclusão tributária. A conversa fica na sessão e é apagada ao sair.
