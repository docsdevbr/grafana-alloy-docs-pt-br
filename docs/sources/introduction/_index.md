---
# SPDX-FileCopyrightText: 2026 Grafana Labs.
# Grafana and the Grafana logo are trademarks owned by Raintank, Inc. dba
# Grafana Labs.
#
# SPDX-License-Identifier: Apache-2.0
# Documentation licensed under the GNU Affero General Public License Version 3.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/docsdevbr/grafana-alloy-docs-pt-br/blob/-/LICENSES/Apache-2.0.txt

source_url: https://github.com/grafana/alloy/blob/v1.20.1/docs/sources/introduction/_index.md
source_revision: 957c4226eebbf1d8e6b4d733f6aa104b0967a382
translation_status: ready

canonical: https://grafana.com/docs/alloy/latest/introduction/
description: >-
  O Grafana Alloy simplifica a coleta de telemetria ao combinar métricas, logs,
  rastros e perfis em um coletor poderoso e independente de fornecedor.
menuTitle: Introdução
title: Introdução ao Grafana Alloy
weight: 10
---

# Introdução ao {{% param "FULL_PRODUCT_NAME" %}}

O {{< param "FULL_PRODUCT_NAME" >}} é um coletor de telemetria de código aberto
que simplifica a coleta e o envio de dados de observabilidade.
Trata-se de uma [distribuição do OpenTelemetry Collector][OpenTelemetry] com
pipelines do Prometheus integrados e suporte nativo para Loki, Pyroscope e
outros backends de observabilidade.

O {{< param "PRODUCT_NAME" >}} coleta métricas, logs, rastros e perfis em uma
solução unificada.
Em vez de executar coletores separados para cada tipo de sinal, você configura
uma única ferramenta que atende a todas as suas necessidades de telemetria.
Essa abordagem reduz a complexidade operacional e oferece flexibilidade para
enviar dados a qualquer backend compatível, seja o Grafana Cloud, uma stack do
Grafana autogerenciada ou outras plataformas de observabilidade.

{{< youtube bFyGd_Sr5W4 >}}

{{< docs/learning-journeys
  title="Envie logs para o Grafana Cloud usando o Alloy"
  url="/docs/learning-journeys/send-logs-alloy-loki/" >}}

## Primeiros passos

- [Instale][Instale] o {{< param "PRODUCT_NAME" >}} em sua plataforma.
- Aprenda [conceitos][conceitos] fundamentais, incluindo componentes, expressões
  e pipelines.
- Siga [tutoriais][tutoriais] para obter experiência prática.
- Explore [cenários do Alloy][cenários] para ver exemplos de configuração do
  mundo real.
- Experimente o workshop [Alloy para iniciantes][iniciantes] para um aprendizado
  interativo baseado em cenários.
- Explore a [referência de componentes][referência] para conhecer os componentes
  disponíveis.

## Saiba mais

- [Por que usar o Alloy][Por que usar o Alloy]: entenda quando o
  {{< param "PRODUCT_NAME" >}} é a escolha certa.
- [Como o Alloy funciona][Como o Alloy funciona]: saiba mais sobre a arquitetura
  e os principais recursos.
- [Requisitos e expectativas][Requisitos]: revise as considerações e restrições
  de implantação.
- [Plataformas suportadas][Plataformas suportadas]: verifique a compatibilidade
  da plataforma.
- [Estime o uso de recursos][Estime o uso de recursos]: planeje sua implantação.
- [Acesso e permissões][Acesso e permissões]: reforço da segurança, identidade,
  exposição de rede e segredos.
- [Migre de outros coletores][migre]: migre do OpenTelemetry Collector,
  Prometheus Agent ou Grafana Agent.

[OpenTelemetry]: https://opentelemetry.io/docs/collector/distributions/
[Instale]: ../set-up/install/
[conceitos]: ../get-started/
[tutoriais]: ../tutorials/
[referência]: ../reference/
[Por que usar o Alloy]: ./why-alloy/
[Como o Alloy funciona]: ./how-alloy-works/
[Requisitos]: ./requirements/
[Plataformas suportadas]: ../set-up/supported-platforms/
[Estime o uso de recursos]: ../set-up/estimate-resource-usage/
[Acesso e permissões]: ../access_permissions/
[migre]: ../set-up/migrate/
[iniciantes]: https://github.com/grafana/Grafana-Alloy-for-Beginners
[cenários]: https://github.com/grafana/alloy-scenarios

## Perguntas frequentes

{{< qa-list >}}
{{< qa question="O que é o Grafana Alloy?" >}}
O Grafana Alloy é um coletor de telemetria de código aberto que simplifica a
coleta e o envio de telemetria.
O Alloy é uma distribuição do OpenTelemetry Collector, um coletor de código
aberto que recebe, processa e envia telemetria.
O Alloy também inclui suporte nativo para o Prometheus, um sistema de coleta de
métricas, e pode enviar dados para o Loki (logs), Pyroscope (perfis) e outros
backends de telemetria.
{{< /qa >}}
{{< qa question="Preciso de um coletor separado para métricas, logs, rastros e
  perfis?" >}}
Não com o Alloy.
Ele foi projetado para coletar métricas, logs, rastros e perfis em uma única
ferramenta, reduzindo a quantidade de coletores que você precisa executar e
manter.
Você ainda pode encaminhar esses dados para o Grafana Cloud, para uma stack
autogerenciada ou para outros backends compatíveis.
{{< /qa >}}
{{< qa question="Como o Grafana Alloy funciona?" >}}
Você cria pipelines a partir de componentes, pequenas unidades funcionais que
realizam uma tarefa específica, como receber dados, transformá-los ou enviá-los
para um backend.
Você conecta os componentes entre si em um arquivo de configuração.
A saída de um componente alimenta a entrada de outro.
O Alloy executa essa configuração como um pipeline contínuo, permitindo que os
dados fluam da origem para o backend sem que você precise gerenciar ferramentas
separadas para cada etapa.
{{< /qa >}}
{{< /qa-list >}}
