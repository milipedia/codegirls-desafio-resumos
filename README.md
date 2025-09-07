Meus Apontamentos sobre AWS - Módulos 1 & 2

Este repositório serve como um resumo dos principais pontos aprendidos durante os módulos 1 e 2 do curso de AWS. O objetivo é consolidar o conhecimento sobre a infraestrutura global da AWS e os conceitos fundamentais de computação com o serviço EC2.

Módulo 1: Fundamentos e Infraestrutura Global da AWS
🔹 Origem e Visão Geral
História: A AWS (Amazon Web Services) foi lançada em 2006, nascendo da necessidade da própria Amazon.com de ter uma infraestrutura de TI escalável e robusta. Eles transformaram essa solução interna em um produto, oferecendo-a como serviço para outras empresas.

Relevância: Entender essa origem ajuda a compreender a filosofia da AWS, focada em escala, resiliência e alta demanda.

🔹 A Infraestrutura Global 🌍
Este é um dos conceitos mais importantes. A estrutura física da AWS é a base para construir qualquer solução na nuvem.

Regiões (Regions): São áreas geográficas isoladas ao redor do mundo (ex: us-east-1 em N. Virginia, sa-east-1 em São Paulo). Recursos criados em uma região são independentes e não são replicados automaticamente para outras, garantindo isolamento contra falhas regionais.

Zonas de Disponibilidade (Availability Zones - AZs): Cada Região é composta por múltiplas AZs. Uma AZ é, essencialmente, um ou mais datacenters com infraestrutura própria (energia, rede, refrigeração). Elas são fisicamente separadas dentro de uma região, mas conectadas por redes de altíssima velocidade e baixa latência.

Propósito das AZs: Permitir a criação de aplicações com Alta Disponibilidade (High Availability). Se uma AZ falhar, a aplicação pode continuar operando a partir de outra AZ na mesma região.

🔹 Fatores para Escolha de uma Região
Ao provisionar um recurso, a escolha da Região é o primeiro passo. A decisão deve considerar:

Compliance e Governança: Leis que exigem que os dados residam em uma localidade específica.

Latência: Para garantir a melhor experiência, escolher a região mais próxima dos usuários finais.

Disponibilidade de Serviços: Nem todos os serviços da AWS estão disponíveis em todas as regiões.

Custo: Os preços dos serviços podem variar entre as regiões.

Módulo 2: Computação na Nuvem com EC2
🔹 Amazon EC2 (Elastic Compute Cloud) 💻
O EC2 é o serviço que oferece capacidade computacional na nuvem, ou seja, servidores virtuais, conhecidos como instâncias. É um serviço do tipo IaaS (Infraestrutura como Serviço).

Famílias de Instâncias: A AWS oferece diferentes "famílias" de instâncias, otimizadas para cargas de trabalho específicas. A escolha correta impacta diretamente a performance e o custo.

Propósito Geral (ex: T, M): Equilíbrio entre CPU, memória e rede. Ideal para servidores web e bancos de dados de pequeno/médio porte.

Otimizadas para Computação (ex: C): Foco em alta performance de CPU. Usadas para processamento intensivo, servidores de jogos e análise de dados.

Otimizadas para Memória (ex: R, X): Grandes quantidades de RAM. Perfeitas para bancos de dados em memória e aplicações que processam grandes datasets.

Otimizadas para Armazenamento (ex: I, D, H): Acesso rápido e de alto volume a dados no disco local. Usadas para Data Warehousing e bancos de dados NoSQL.

🔹 Armazenamento para EC2: EBS e S3
Amazon EBS (Elastic Block Store) 💾:

É um serviço de armazenamento em bloco, funcionando como um "HD virtual" de rede que você anexa a uma instância EC2.

Ideal para armazenar o sistema operacional, bancos de dados e arquivos que exigem acesso rápido e persistente.

Permite a criação de Snapshots (cópias de backup), que podem ser usados para restaurar dados ou mover volumes entre AZs e Regiões.

Amazon S3 (Simple Storage Service) 📦:

É um serviço de armazenamento de objetos, projetado para alta durabilidade (99.999999999%) e escalabilidade.

Usado para armazenar arquivos estáticos (imagens, vídeos), backups, logs e grandes volumes de dados (Big Data).

Oferece diferentes classes de armazenamento (S3 Standard, S3-IA, S3 Glacier) para otimizar custos com base na frequência de acesso aos dados.

🔹 Modelos de Compra e Otimização de Custos 💰
Gerenciar os custos é fundamental. A AWS oferece flexibilidade nos modelos de precificação do EC2.

On-Demand (Sob Demanda): Pague por hora ou segundo, sem compromisso. É flexível e ideal para cargas de trabalho imprevisíveis ou para desenvolvimento e testes.

Instâncias Reservadas (Reserved Instances): Comprometa-se com um contrato de 1 ou 3 anos em troca de descontos significativos (até 72%). Perfeito para aplicações com demanda estável e previsível.

Instâncias Spot: Utilize a capacidade computacional ociosa da AWS com descontos de até 90%. A AWS pode retomar a instância a qualquer momento. Ideal para cargas de trabalho tolerantes a interrupções, como processamento em lote e renderização.
