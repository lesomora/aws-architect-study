# Aula 01 Fundamentos - AWS Architect 

O que é o Global Infrastructure ? 

Os serviços da aws são divididos por zonas de disponibilidades espalhadas pelo mundo, entretanto, existem serviços com caracter Global. Isto é, independente da zona de disponibilidade (AZ) você terá aquele serviço disponivel. 

Quais os componentes do Global Infrastructure ? 

* AWS Regions
* AWS Availability Zones
* AWS Datacenters
* AWS Edge Locations (Points of Presence)

O que é o AWS Regions ? 

O AWS region são clusters de datacenters que estão dimensionados pelo mundo, os nomes das regiões são definidas pela localidade e pela quantidade de datacenters existente naquela localidade, outro ponto importante é que alguns serviços podem estar disponiveis apenas numa determinada região. Exemplo de uma região: 

|Nome da região| datacenters | 
|--------------|-------------|
|US East (N. Virginia)| us-east-1, us-east-2, us-east-3| 

---
**Pergunta de Exame**

Qual região devemos escolher para fazer o deploy da nossa aplicação ?

Existem alguns pontos que devem ser considerados, logo a resposta depende. Abaixo as premissas que devem ser consideradas ao fazer o deploy de sua aplicação numa região da aws: 
 *  Compliance: Caso sua aplicação tenha alguma implicação legal ou governamental, isto é, por exemplo um banco no Brasil não pode operar com sua infraestrutura e armazenamento de dados nos Estados Unidos. 
 * Proximity: A verdadeira vantagem da AWS é a possibilidade de prover infraestrutura e serviços mais próximos ao seu usuário, sendo assim deve considerar a localidade do seu deploy perto dos seus consumidores. Assim reduzindo a latência.
 * Available Services: Com novos serviços e funcionalidades sendo lançadas, alguns destes novos recursos podem estar disponiveis apenas em zonas de disponibilidade especificas.
 * Pricing: O preço varia de acordo com a região, caso tenha muito *dataout*. Os preços dos serviços da aws podem impactar o seu projeto, sendo assim, o preço é um balizador importante na hora de definir a estratégia de deployment do seu serviço.
---

O que é uma AZ Availability Zones (zona de disponibilidade) ?
 
A zona de disponibilidade (AZ - Availability Zones) é o datacenter, normalmente uma região pode ter três AZ com até no máximo 6 zonas de disponibilidade. Cada zona de disponibilidade é redudante em energia, rede e conexão de alta performance com baixa latência. Cada zona de disponibilidade é separada da outra fisicamente em uma distancia geografica, visando diminuir a propabilidade de desastre. 

![aws region](/assets/aula01/aws_regions_az.png)

O que são os pontos de presença (Edge Locations) ?

O ponto de presença possibilita entregar serviços com baixa latência ao usuário. Existem mais de 400 pontos de presença no mundo. 

---
**Pergunta de Exame**

Classifique os serviços abaixo como Global Services e Region-scoped 

:globe_with_meridians: - Global Service
:round_pushpin: - Region-scoped 

|Nome do Serviço | Global or Region Scoped | 
|----------------|--------------------|
|IAM - Identity and Access Management | :globe_with_meridians: |
|DNS - Route 53 | :globe_with_meridians: |
|CDN - CloudFront | :globe_with_meridians: | 
|WAF - Web Application Firewall | :globe_with_meridians: | 
|Amazona ECS - Infraestrutura como serviço | :round_pushpin: |
|Elastic Beanstalk - Plataforma como serviço | :round_pushpin: |
|Lambda - Funcionalidade como serviço |:round_pushpin:  |
|Rekognition - Software como serviço |:round_pushpin: |

---

