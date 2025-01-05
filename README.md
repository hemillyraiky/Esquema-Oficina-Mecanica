# Oficina Mecânica - Banco de Dados Relacional

Este projeto consiste no desenvolvimento de um modelo lógico de banco de dados para gerenciar informações relacionadas a uma oficina mecânica. O sistema foi projetado para organizar dados de clientes, veículos, mecânicos, ordens de serviço, peças e serviços de forma eficiente e estruturada.

## Descrição do Sistema

O objetivo principal do banco de dados é permitir o registro, controle e consulta de informações sobre as ordens de serviço realizadas na oficina. Ele facilita o acompanhamento do histórico de veículos, a gestão de custos e a identificação de serviços e peças utilizados.

## Estrutura do Banco de Dados

### **Entidades Principais**
1. **Cliente**
   - Armazena os dados dos clientes.
   - **Atributos**:
     - `idCliente`: Identificador único do cliente.
     - `nome`: Nome do cliente.
     - `endereco`: Endereço do cliente.
     - `telefone`: Telefone do cliente.

2. **Veículo**
   - Relaciona veículos aos seus respectivos proprietários (clientes).
   - **Atributos**:
     - `idVeiculo`: Identificador único do veículo.
     - `placa`: Placa do veículo.
     - `modelo`: Modelo do veículo.
     - `ano`: Ano de fabricação do veículo.
     - `idCliente`: Identificador do cliente proprietário.

3. **Mecânico**
   - Contém informações sobre os mecânicos da oficina.
   - **Atributos**:
     - `idMecanico`: Identificador único do mecânico.
     - `nome`: Nome do mecânico.
     - `endereco`: Endereço do mecânico.
     - `especialidade`: Área de especialização do mecânico.

4. **Ordem de Serviço (OS)**
   - Centraliza as informações das ordens de serviço.
   - **Atributos**:
     - `idOS`: Identificador único da OS.
     - `dataEmissao`: Data de emissão da ordem.
     - `valorTotal`: Valor total da ordem.
     - `status`: Status da ordem (ex.: Em andamento, Concluída).
     - `dataConclusao`: Data de conclusão da ordem.
     - `idVeiculo`: Identificador do veículo relacionado.

5. **Peça**
   - Armazena as informações sobre peças utilizadas.
   - **Atributos**:
     - `idPeca`: Identificador único da peça.
     - `descricao`: Descrição da peça.
     - `valor`: Valor unitário da peça.

6. **Serviço**
   - Contém dados sobre os serviços prestados.
   - **Atributos**:
     - `idServico`: Identificador único do serviço.
     - `descricao`: Descrição do serviço.
     - `valorMaoDeObra`: Valor da mão de obra.

### **Entidades Associativas**
1. **OS Peça**
   - Relaciona as peças utilizadas em uma ordem de serviço.
   - **Atributos**:
     - `idOS`: Identificador da OS.
     - `idPeca`: Identificador da peça.
     - `quantidade`: Quantidade da peça utilizada.
     - `valor`: Valor total das peças utilizadas.

2. **OS Serviço**
   - Registra os serviços realizados em uma ordem de serviço.
   - **Atributos**:
     - `idOS`: Identificador da OS.
     - `idServico`: Identificador do serviço.
     - `quantidade`: Quantidade de vezes que o serviço foi realizado.
     - `valor`: Valor total do serviço.

3. **OS Mecânico**
   - Relaciona os mecânicos que participaram da execução de uma ordem de serviço.
   - **Atributos**:
     - `idOS`: Identificador da OS.
     - `idMecanico`: Identificador do mecânico.

## Relacionamentos

- Um cliente pode possuir vários veículos (1:N).
- Um veículo pode estar associado a várias ordens de serviço (1:N).
- Uma ordem de serviço pode incluir múltiplos serviços e peças, e envolver vários mecânicos (N:N).
- Os serviços e peças são armazenados em tabelas específicas para facilitar a gestão e a recuperação de informações.


> **Autor:** Hemilly Araujo 
> **Projeto desenvolvido com base nos requisitos de oficinas mecânicas.**
