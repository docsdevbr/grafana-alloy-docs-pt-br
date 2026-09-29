---
# SPDX-FileCopyrightText: 2026 Grafana Labs.
# Grafana and the Grafana logo are trademarks owned by Raintank, Inc. dba
# Grafana Labs.
#
# SPDX-License-Identifier: Apache-2.0
# Documentation licensed under the GNU Affero General Public License Version 3.
# The original work was translated from English into Brazilian Portuguese.
# https://github.com/docsdevbr/grafana-loki-docs-pt-br/blob/-/LICENSES/Apache-2.0.txt

source_url: https://github.com/grafana/alloy/blob/v1.20.1/docs/sources/_index.md
source_revision: 95e12cf8961fabc9db6858f7e79bde5c814a07a0
translation_status: ready

canonical: https://grafana.com/docs/alloy/latest/
title: Grafana Alloy
description: >-
  O Grafana Alloy é uma distribuição do OTel Collector independente de
  fornecedor.
weight: 350
cascade:
  ALLOY_RELEASE: v1.20.1 # x-release-please-version
  OTEL_VERSION: v0.161.0
  PROM_WIN_EXP_VERSION: v0.31.3
  SNMP_VERSION: v0.29.0
  BEYLA_VERSION: v3.35.0
  FULL_PRODUCT_NAME: Grafana Alloy
  PRODUCT_NAME: Alloy
  FULL_OTEL_ENGINE: Alloy OpenTelemetry Engine
  OTEL_ENGINE: OTel Engine
  DEFAULT_ENGINE: Default Engine
hero:
  title: Grafana Alloy
  level: 1
  image: /media/docs/alloy/alloy_icon.png
  width: 110
  height: 110
  description: >-
    O Grafana Alloy reúne os pontos fortes dos principais coletores em uma única
    solução.
    Seja para observar aplicações, infraestrutura ou ambos, o Grafana Alloy pode
    coletar, processar e exportar sinais de telemetria para escalar e preparar
    sua estratégia de observabilidade para o futuro.
cards:
  title_class: pt-0 lh-1
  items:
    - title: Introdução ao Alloy
      href: ./introduction/
      description: Saiba o que o Alloy pode fazer por você.
    - title: Instale o Alloy
      href: ./set-up/install/
      description: >-
        Aprenda a instalar e desinstalar o Alloy no Docker, Kubernetes, Linux,
        macOS ou Windows.
    - title: Execute o Alloy
      href: ./set-up/run/
      description: >-
        Aprenda a iniciar, reiniciar e parar o Alloy após a instalação.
    - title: Configure o Alloy
      href: ./configure/
      description: >-
        Aprenda a configurar o Alloy no Kubernetes, Linux, macOS ou Windows.
    - title: Migre para o Alloy
      href: ./set-up/migrate/
      description: >-
        Aprenda a migrar para o Alloy a partir do Grafana Agent Operator,
        Prometheus, Promtail, Grafana Agent Static ou Grafana Agent Flow.
    - title: Colete dados do OpenTelemetry
      href: ./collect/opentelemetry-data/
      description: >-
        Aprenda a configurar o envio de dados do OpenTelemetry, configurar o
        processamento em lote e receber dados do OpenTelemetry via OTLP.
    - title: Conceitos
      href: ./get-started/
      description: >-
        Saiba mais sobre componentes, módulos, clustering e a sintaxe de
        configuração do Alloy.
    - title: Referência
      href: ./reference/
      description: >-
        Consulte a documentação de referência sobre ferramentas de linha de
        comando, blocos de configuração, componentes e biblioteca padrão.
---

{{< docs/hero-simple key="hero" >}}

---

# Visão geral

{{< figure src="/media/docs/alloy/alloy_diagram_v2.svg" alt="Diagrama de fluxo do Alloy" >}}

**Colete toda a sua telemetria com um único produto**

Escolher as ferramentas adequadas para coletar, processar e exportar dados de
telemetria pode ser uma experiência confusa e dispendiosa.
A ampla gama de telemetria que você precisa processar e os coletores escolhidos
podem variar significativamente, dependendo dos seus objetivos de
observabilidade.
Além disso, você enfrenta o desafio de atender às necessidades em constante
evolução da sua estratégia de observabilidade.
Por exemplo, você pode precisar inicialmente apenas de observabilidade de
aplicações, mas depois descobrir que precisa adicionar observabilidade de
infraestrutura.
Muitas organizações gerenciam e configuram múltiplos coletores para lidar com
esses desafios, o que introduz mais complexidade e possíveis erros em suas
estratégias de observabilidade.

**Todos os sinais: aplicações, infraestrutura ou ambos**

O {{< param "FULL_PRODUCT_NAME" >}} possui pipelines nativas para os principais
sinais de telemetria, como Prometheus e OpenTelemetry, e para bancos de dados
como Loki e Pyroscope.
Isso permite trabalhar com logs, métricas, rastros e até mesmo oferecer suporte
robusto para profiling.

**Observabilidade de nível empresarial**

O {{< param "FULL_PRODUCT_NAME" >}} aumenta a confiabilidade e oferece recursos
avançados para necessidades corporativas, como clusters de frotas e
balanceamento de cargas de trabalho.
O recurso de
[Gerenciamento de frotas](https://grafana.com/docs/grafana-cloud/send-data/fleet-management/)
do Grafana ajuda você a gerenciar múltiplas implantações do
{{< param "FULL_PRODUCT_NAME" >}} em escala.

## Explore

{{< card-grid key="cards" type="simple" >}}
