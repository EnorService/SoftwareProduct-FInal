# Diagramas da Lanchonete Ágil

Abra [Diagramas_Lanchonete_Agil.pdf](Diagramas_Lanchonete_Agil.pdf) para consultar os três diagramas.

1. **Classes.** Mostra a classe de persistência `ExcelDB`, a exceção `DataError` e os registros lógicos que o Python representa como dicionários.
2. **Casos de uso.** Mostra as operações de atendimento e administração. Operador representa quem usa os módulos habilitados. A senha administrativa protege o painel que configura esses módulos.
3. **MER.** Representa as sete abas de `data/lanchonete.xlsx`. PK e FK representam chaves lógicas. O código Python mantém os relacionamentos e o Excel armazena os registros. A aba `Configuracoes` tem chaves próprias e fica sem relacionamento com as demais.

Os arquivos `.dot` são os fontes do PDF e podem ser editados com ferramentas compatíveis com Graphviz. Classes e casos de uso também estão disponíveis em PlantUML.

Ao criar um pedido, o sistema grava os itens e o total com status **ABERTO**. A efetivação valida o estoque, dá baixa nas quantidades e muda o status para **CONFIRMADO**. O cancelamento de um pedido aberto muda o status para **CANCELADO**.

Na lista de pedidos, a exclusão remove o pedido e seus itens. Quando o pedido está **CONFIRMADO**, a exclusão devolve as quantidades ao estoque. O sistema conserva o maior identificador excluído em `Configuracoes` para evitar reutilizar números de pedido.
