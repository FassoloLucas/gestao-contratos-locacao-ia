# Regras contábeis e fiscais

As regras que definem os números da plataforma. Elas apoiam a análise e não substituem a revisão contábil e tributária de cada caso.

## Contabilidade e resultado

- **Sinal da DRE:** saldo = crédito − débito. Receita positiva, despesa negativa; na análise horizontal, variação positiva é sempre melhora, inclusive em despesa.
- **Lote de encerramento:** o lançamento de 31/12 que zera o resultado contra o patrimônio líquido é excluído da DRE e do Orçamento e mantido no Livro Razão. Sem essa exclusão, dezembro e o ano fechado aparecem distorcidos.
- **Hierarquia de contas:** calculada pela conta-pai do plano do ERP, não pelo prefixo do número da conta.
- **Livro Razão:** saldo = débito − crédito, com natureza D ou C. Começa do zero no período escolhido; lançamentos cancelados ficam fora.
- **CMV:** o Dashboard usa o CMV contábil. Nos relatórios, o gerencial só substitui o contábil no mês em que todas as empresas escolhidas têm valor; caso contrário, a DRE usa o contábil e avisa.
- **Consumo do orçamento:** débito − crédito das contas de despesa, pelo saldo contábil, com as mesmas empresas da DRE e sem o lote de encerramento. Uma conta pertence a um único setor por ano; ano sem vínculo próprio herda o do último ano anterior.
- **Cobertura documental:** na Análise de Despesas, documentos ÷ débito da conta. O débito é a base certa porque rateios e estornos a crédito reduzem o saldo e inflariam a cobertura. O que não tem documento aparece separado, para a soma fechar com a DRE.
- **DRE por loja:** saldo contábil por filial, sem o lote de encerramento. O aluguel entra pelo valor fixo de cada loja na vigência, no lugar da amortização e dos juros do direito de uso. Receita líquida = venda + acordo − devoluções, e cada grupo é a soma das suas linhas, nunca a conta sintética do plano.

## Arrendamento (CPC 06)

- Passivo = valor presente das parcelas pela taxa do contrato.
- Juros a apropriar = nominal − valor presente.
- Curto prazo = parcelas dos próximos 12 meses.
- O arredondamento é feito nos saldos acumulados, para cada mês ficar a até um centavo do valor exato e os saldos zerarem no fim do contrato.
- O reconhecimento e os pagamentos são lançados em empresas diferentes no ERP, então o saldo só é comparável no consolidado, que é como a conciliação compara.
- Evento que atinge uma competência fechada é recusado até ela ser reaberta.

## Depreciação

- Linear, a partir do mês de ativação (mês cheio).
- Quota = custo ÷ vida útil, ou a quota fixa do bem; o último mês lança o residual inteiro e o bem nunca é depreciado acima do custo.
- Conciliação mensal com o saldo do ERP sem tolerância: qualquer centavo de diferença vira alerta.
- A reclassificação da nota do imobilizado a classificar é reconhecida pela própria nota e pelo valor, sem duplicar o bem.

## Fiscal

- **Período:** conferência, FCP e DIFAL usam a data de lançamento, que pode diferir da emissão, e o último dia do período entra inteiro.
- **Tolerância:** diferenças de até R$ 0,02 não são apontadas. Os valores são calculados em decimal, sem erro de ponto flutuante.
- **FCP:** o FCP é somado ao ICMS, e o FCP-ST ao ICMS-ST, antes de comparar com o ERP.
- **Unidade:** quando o lançamento está na unidade tributável, a comparação usa quantidade e preço tributáveis do XML; nos demais casos, converte pela embalagem.
- **CFOP:** compara o sentido da operação (entrada ou saída) e a presença de ST, não a igualdade integral do código.
- **PIS/COFINS:** compara o destaque do XML com a importação; com CST fora das faixas de crédito e sem crédito, diferença contra zero é ignorada.
- **Dados faltantes:** dado essencial ausente vira "dados incompletos", fora da contagem de divergências.
- **FCP estadual:** 2% sobre a base de ICMS das alíquotas sujeitas ao fundo, em entradas não canceladas e saídas normais. O saldo segue a consulta conciliada com a apuração.
- **DIFAL:** entradas com CFOP 2551 e 2556; DIFAL e FCP vêm separados, e a soma é o total a recolher.
- **Emissões canceladas:** NF-e canceladas e inutilizadas na SEFAZ confrontadas com o livro fiscal na emissão e na entrada da filial de destino, com situação Pendente, Atenção ou OK.
- **F100:** cada linha é arredondada ao centavo (meio para cima) antes da soma; créditos normais e adicional da LC 224 nunca são somados juntos.
- **Resumo SPED:** soma C190, C590, D190 e D590 por CFOP, CST e alíquota. Conferido contra o E110: o ICMS das entradas bate com os créditos e o das saídas com os débitos. Registros como C490 e C850 ficam fora da soma, com aviso na tela.

## Conferências contra a fonte oficial

- O consumo do Orçamento foi conferido com o balancete.
- As consultas de FCP e DIFAL são as que foram conciliadas com os PDFs da apuração.
- A depreciação foi aceita na implantação com a conciliação da primeira competência contra o saldo do ERP.
