---
# SPDX-FileCopyrightText: 2026 Grafana Labs.
# Grafana and the Grafana logo are trademarks owned by Raintank, Inc. dba
# Grafana Labs.
#
# SPDX-License-Identifier: Apache-2.0
# Documentation licensed under the GNU Affero General Public License Version 3.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/docsdevbr/grafana-alloy-docs-pt-br/blob/-/LICENSES/Apache-2.0.txt

source_url: https://github.com/grafana/alloy/blob/v1.20.1/docs/sources/introduction/how-alloy-works.md
source_revision: 0533d38563cee9203b3b496e1bc461bdf5eb328e
translation_status: ready

canonical: https://grafana.com/docs/alloy/latest/introduction/how-alloy-works/
description: >-
  Saiba como o Grafana Alloy funciona e onde ele se encaixa na sua arquitetura
  de observabilidade.
menuTitle: Como o Alloy funciona
title: Como o Grafana Alloy funciona
weight: 220
---

# Como o {{% param "FULL_PRODUCT_NAME" %}} funciona

Compreender a arquitetura e o design do {{< param "PRODUCT_NAME" >}} ajuda você
a utilizá-lo de forma eficaz.

## Onde o {{% param "PRODUCT_NAME" %}} se encaixa

Uma configuração típica de observabilidade possui três camadas: fontes de dados
que geram telemetria, ferramentas de coleta que as reúnem e processam, e
backends de armazenamento com frontends de visualização para consultar e
explorar os dados.

O {{< param "PRODUCT_NAME" >}} opera na camada de coleta, posicionando-se entre
suas fontes de dados e seus backends de armazenamento.
Ele atua como uma ponte entre eles, desempenhando três funções principais em seu
pipeline de telemetria.

### Coletar dados de telemetria

O {{< param "PRODUCT_NAME" >}} coleta telemetria de qualquer fonte em sua
infraestrutura.
Você pode configurá-lo para realizar a raspagem de endpoints do Prometheus em
busca de métricas ou definir receptores para aceitar dados enviados via
protocolo OpenTelemetry.
Ele monitora arquivos de log e lê saídas do sistema para capturar logs de
aplicações e da infraestrutura.
A descoberta de serviços localiza automaticamente recursos em ambientes
Kubernetes, Docker ou de nuvem, sem exigir configuração estática.
Você também pode integrá-lo a bancos de dados, filas de mensagens e outros
sistemas para capturar telemetria de fontes especializadas.

### Transformar e processar dados

O processamento da telemetria antes do envio para backends otimiza custos e
melhora a qualidade dos dados.
Crie filtros para descartar dados indesejados ou ocultar informações sensíveis,
como tokens e credenciais, dos logs antes que cheguem ao armazenamento.
Adicione rótulos, metadados ou informações contextuais para enriquecer seus
dados, por exemplo, extraia o nome do provedor de nuvem de IDs de instâncias
para criar rótulos de agregação úteis.
Padronize nomes de atributos entre serviços quando diferentes equipes utilizarem
convenções de nomenclatura inconsistentes.
Implemente estratégias de amostragem para reduzir o volume de dados, preservando
ao mesmo tempo os sinais necessários para a resolução de problemas.
Converta formatos, como transformar métricas do Prometheus para o formato
OpenTelemetry, para garantir a compatibilidade com seus backends.
Defina regras de roteamento para enviar diferentes tipos de dados para destinos
distintos, com base em seus requisitos operacionais.

### Enviar para backends

O {{< param "PRODUCT_NAME" >}} entrega a telemetria processada a qualquer
sistema de armazenamento de sua escolha.
Envie dados para o Grafana Cloud para obter observabilidade gerenciada ou
exporte-os para componentes da sua stack Grafana autogerenciada.
Conecte-se a qualquer banco de dados compatível com Prometheus para métricas e a
qualquer backend compatível com OpenTelemetry para todos os tipos de sinal.
Grave em múltiplos destinos simultaneamente, enviando os mesmos dados para
sistemas diferentes ou roteando tipos de dados distintos para backends
especializados.

## Arquitetura baseada em componentes

O {{< param "PRODUCT_NAME" >}} utiliza [componentes][] modulares que funcionam
como blocos de construção.
Cada componente executa uma tarefa específica, como coletar métricas de
endpoints do Prometheus, receber dados do OpenTelemetry, transformar e filtrar
telemetria ou enviar dados para backends.

Você conecta esses componentes para [criar pipelines][] que atendam exatamente
às suas necessidades.
Essa abordagem modular torna as configurações mais fáceis de entender, testar e
manter.

## Pipelines programáveis

O {{< param "PRODUCT_NAME" >}} utiliza uma
[linguagem de configuração rica e baseada em expressões][syntax], permitindo
referenciar dados de um componente em outro, criar configurações dinâmicas que
respondem a condições variáveis, construir pipelines reutilizáveis que podem ser
compartilhados entre equipes e usar [funções][expressions] integradas para
transformar e filtrar dados.

## Pipelines personalizados e compartilháveis

Você pode criar [componentes personalizados][] que combinam vários componentes
em uma única unidade reutilizável.
Compartilhe esses componentes personalizados com sua equipe ou com a comunidade
por meio do [sistema de módulos][modules].
Utilize módulos prontos da comunidade ou crie os seus próprios.

## Recursos prontos para empresas

À medida que seus sistemas se tornam mais complexos, o
{{< param "PRODUCT_NAME" >}} acompanha seu crescimento.
O recurso de [clustering][] permite configurar instâncias para formar um
cluster, garantindo a distribuição automática de carga de trabalho e alta
disponibilidade.
A configuração centralizada recupera definições de servidores remotos para
facilitar o gerenciamento de frotas.
Recursos nativos do Kubernetes permitem interagir diretamente com os recursos do
Kubernetes, sem a necessidade de aprender operadores específicos.

## Ferramentas de depuração integradas

O {{< param "PRODUCT_NAME" >}} inclui uma
[interface de usuário integrada][debug] que ajuda você a visualizar seus
pipelines de componentes, inspecionar estados e saídas de componentes,
solucionar problemas de configuração e monitorar o desempenho.

## Padrões de implantação

Escolha o [padrão de implantação][deploy] que melhor se adapta à sua
arquitetura.

**Implantação na borda:** implante o {{< param "PRODUCT_NAME" >}} próximo às
suas fontes de dados para obter latência mínima.
Execute-o como um DaemonSet no Kubernetes para coletar dados de todos os nós,
instale-o em cada host para monitoramento de infraestrutura ou implante-o junto
às aplicações para processamento local.

**Implantação como gateway:** implante o {{< param "PRODUCT_NAME" >}} como um
gateway centralizado.
Configure suas aplicações para enviar telemetria aos gateways do
{{< param "PRODUCT_NAME" >}}, que processam e encaminham os dados para backends.
As aplicações precisam conhecer apenas os endpoints do gateway.

**Implantação híbrida:** combine as abordagens de borda e gateway.
Implante instâncias na borda para lidar com a coleta e filtragem iniciais
próximas às fontes e, em seguida, encaminhe os dados para instâncias de gateway
para agregação e processamento final.
Esse padrão reduz o uso de largura de banda e permite a aplicação centralizada
de políticas, mantendo as capacidades de processamento local.

## Integrações

O {{< param "PRODUCT_NAME" >}} integra-se ao Grafana Cloud e a stacks do Grafana
autogerenciadas, roteando métricas para o Mimir, logs para o Loki, rastros para
o Tempo e perfis para o Pyroscope.
Ele também funciona com o ecossistema Prometheus mais amplo, graças à
compatibilidade total com o formato de exposição do Prometheus e mecanismos de
descoberta de serviço, bem como com qualquer backend compatível com
OpenTelemetry por meio do suporte a OTLP.

Você também pode conectar-se a outros ecossistemas, incluindo InfluxDB,
Elasticsearch e plataformas de nuvem como AWS, Google Cloud Platform e Azure.

## Próximos passos

- Revise os [requisitos e expectativas][requirements] para entender as
  considerações de implantação.
- [Instale][Install] o {{< param "PRODUCT_NAME" >}} para começar.
- Aprenda os [conceitos][Concepts] fundamentais, incluindo componentes,
  expressões e pipelines.
- Siga os [tutoriais][tutorials] para obter experiência prática.
- Explore a [referência de componentes][reference] para ver os componentes
  disponíveis.

[requirements]: ../requirements/
[Install]: ../../set-up/install/
[Concepts]: ../../get-started/
[tutorials]: ../../tutorials/
[reference]: ../../reference/
[componentes]: ../../get-started/components/
[criar pipelines]: ../../get-started/components/build-pipelines/
[syntax]: ../../get-started/syntax/
[expressions]: ../../get-started/expressions/
[componentes personalizados]: ../../get-started/components/custom-components/
[modules]: ../../get-started/modules/
[clustering]: ../../get-started/clustering/
[debug]: ../../troubleshoot/debug/
[deploy]: ../../set-up/deploy/
