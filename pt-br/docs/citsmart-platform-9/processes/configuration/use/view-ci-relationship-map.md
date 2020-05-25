Title: Ver mapa de relacionamento de um IC

# Ver mapa de relacionamento de um IC

O mapa de relacionamento é o local onde você poderá ter, visualmente, um panorama da árvore de relacionamento que existe entre ICs e ICs e Serviços. Nele você poderá usar diversos filtros para moldar o tipo de resultado que será apresentado.

## O que fazer antes

A visualização do mapa de relacionamento está condicionada ao seguinte cenário:

- [X] Ter realizado o inventário de ICs e ter construído a árvore de relacionamentos (ver: [Relacionar Item de Configuração a um Serviço][2])

## Procedimento

1. Acessar a funcionalidade pelo menu Processos > Gerência de Configuração > CMDB;

2. Clicar em "Visualizar mapa de relacionamento";

3. Na tela de Mapa de Desenho de IC, estão disponível os seguintes campos:

| Campo | Descrição |
|-------|-----------|
|Filtro| a.  **Causa e Efeito**: Visualização Padrão do sistema que consiste em na demonstração gráfica tanto abaixo quanto acima do IC nó selecionado; b. **Análise de Impacto**: Visualização que consiste na demonstração gráfica dos itens desenhados abaixo do nó selecionado;  c. **Análise de Causa Raiz**: visualização que consiste na demonstração gráfica dos itens desenhados acima do nó selecionado.|
|Nível| de 1 a 4 |
|Ícones| **Seta**: permite arrastar o mapa; **Lupa**: permite aumentar ou reduzir o zoom do mapa.

## Ver capacidade total do IC

É possível visualizar o total de capacidade e seus indicadores através do mapa de relacionamento do IC.
Além disso, o usuário poderá prever a capacidade dos ICs relacionados. A plataforma captura e mostra todos os tempos de resposta do IC e, se o total exceder o limite configurado, uma notificação pode ser enviada ao usuário ou publicada no portal. 
Ao clicar em **Exibir capacidade total**, temos as seguintes informações:

|Campo|Descrição|
|-------|-------|
|Característica|O item de configuração relacionado|
|Indicador|Apresenta os indicadores para a capacidade configurada pelo seu total e médio|
|Medido|O valor medido pela ferramenta, levando em consideração os indicadores. Apresenta também o total e o meio, no entanto, com a adição de uma representação visual da quantidade utilizada|
|Previsão|Aqui é possível prever a capacidade total, ou seja, você pode definir uma porcentagem para informá-lo quando um determinado valor for atingido. A ferramenta informará se a capacidade atual está correta ou se está atingindo sua capacidade total.|

## Relacionado

[Relacionar Item de Configuração a um serviço][1]

[1]:/pt-br/citsmart-platform-9/processes/configuration/use/create-ic-relationship.html

[2]:/pt-br/citsmart-platform-9/processes/configuration/use/create-ic-relationship.html
