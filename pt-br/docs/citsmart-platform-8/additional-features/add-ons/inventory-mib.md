Title: Fazer inventário de hardware a partir de MIBs (SNMP)

# Fazer inventário de hardware a partir de MIBs (SNMP)

## O que fazer antes

- [X] É necessário estar rodando a última versão do INVENTORY;
- [X] No arquivo standalone-full.xml deve ser adicionada a propriedade snmp.oid.repository.directory contendo o caminho da pasta onde estarão os arquivos xml com o layout;

´snmp.oid.repository.directory´

## Criar o layout

Modelo:

```xml
<SEU-TIPO-ITEM oid-validator="(OID de uma propriedade específica que irá permitir que seja interpretado o resto do arquivo. Caso não retorne valor, o TIPO-ITEM não é criado.)">
                <SUA-CARACTERISTICA>(OID da informação desejada)</SUA-CARACTERISTICA>
                <CARACTERISTICA-EM-HEXA type="hex">(OID da informação que o valor retornado precisa ser convertido de HEXADECIMAL)</CARACTERISTICA-EM-HEXA>
</SEU-TIPO-ITEM>
```
 
Exemplo:

```xml
<IMPRESSORA oid-validator=".1.3.6.1.2.1.43.5.1.1.16.1">
                <NAME>.1.3.6.1.2.1.43.5.1.1.16.1</NAME>
                <DESCRIPTION type="hex">.1.3.6.1.2.1.43.5.1.1.16.1</DESCRIPTION>
                <QTD-PAGINAS-IMPRESSAS>.1.3.6.1.2.1.43.10.2.1.4.1.1</QTD-PAGINAS-IMPRESSAS>
                <CAPACIDADE-TOTAL-TONER>.1.3.6.1.2.1.43.11.1.1.8.1.1</CAPACIDADE-TOTAL-TONER>
                <CAPACIDADE-ATUAL-TONER>.1.3.6.1.2.1.43.11.1.1.9.1.1</CAPACIDADE-ATUAL-TONER>
</IMPRESSORA>
```

!!! note "Observações"

    1. Os arquivos de layout podem ter qualquer nome. Todos os arquivos da pasta serão interpretados, portanto só poderão existir arquivos XML dentro dela;
    2. Caso exista mais de um layout, pode ser colocado dentro do mesmo arquivo ou em arquivos diferentes. Só deve-se respeitar o formato de XML;
    
!!! exemple "Links úteis"

    1. http://www.oidview.com/mibs/ - Repositório contendo milhares de MIB’s separado por fabricantes.
    2. http://ireasoning.com/mibbrowser.shtml - Ferramenta MibBrowser que pode auxiliar na coleta das OID’s.
    
