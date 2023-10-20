# Documento de Deploy do Back-end

## Versionamento

| Versão | Data | Modificação | Autor |
|--|--|--|--|
|1.0| 14/10/2023 | Criação do documento | Vitor Kühl |

## Introdução

<p align = "justify"> &emsp;&emsp; A finalidade este documento é apresentar de forma geral como foi o processo para realizar o deploy do back-end do MeasureSoftGram e quais foram as dificuldades e soluções encontradas. </p>

<p align = "justify"> &emsp;&emsp; Através desse documento, é possível obter um melhor entendimento de como foi o processo do deploy do back-end do service do MeasureSoftGram, quais ferramentas foram utilizadas para que o processo fosse concluído com êxito, além de documentar quais foram as dificuldades encontradas durante este processo.</p>

### Visão Geral

* Introdução: Apresenta uma visão geral sobre o conteúdo dessa documentação;
* Processo de Deploy: Descreve detalhadamente como foi o processo do deploy do back-end;
* Referências: Emprega as fontes utilizadas nas pesquisas para relacionar as publicações que foram consultadas e citadas.

## Processo de Deploy

Iniciamos nossa tentativa de deploy através da Amazon Web Services (AWS). Configuramos instâncias no EC2 (Elastic Compute Cloud) para a hospedagem da nossa aplicação e usamos o RDS (Relational Database Service) para gerenciar nosso banco de dados. No entanto, após finalizarmos o deploy na AWS, encontramos um problema: ao tentar acessar a aplicação pelo IP público, a página não carregava.

Diante desse contratempo e da necessidade de um deploy rápido devido ao nosso cronograma apertado, decidimos procurar uma solução alternativa. Foi nesse contexto que escolhemos o Railway como nossa ferramenta de deploy. A transição para o Railway mostrou-se uma decisão acertada. A experiência com ele foi tranquila e conseguimos realizar o deploy sem enfrentar as dificuldades que tivemos com a AWS.

Após a conclusão do deploy no Railway, tentamos novamente realizar o deploy na AWS e identificar o problema existente. Após diversas pesquisas, criamos uma instância na S3 Storage, que é é um serviço de armazenamento de objetos, e com essa instância criada e os devidos códigos executados, o deploy foi efetuado e finalmente conseguimos acessar a interface do back-end. Porém, devido as facilidades do deploy no Railway, decidimos manter o deploy lá, deixando o deploy na AWS como reserva para caso de emergência.

