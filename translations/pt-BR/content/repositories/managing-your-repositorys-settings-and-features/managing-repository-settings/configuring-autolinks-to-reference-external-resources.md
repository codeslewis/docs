---
title: Configurar links automáticos para fazer referência a recursos externos
intro: Você pode adicionar links automáticos para recursos externos como problemas do JIRA e tíquetes do Zendesk a fim de ajudar a otimizar o fluxo de trabalho.
product: '{% data reusables.gated-features.autolinks %}'
redirect_from:
  - /articles/configuring-autolinks-to-reference-external-resources
  - /github/administering-a-repository/configuring-autolinks-to-reference-external-resources
  - /github/administering-a-repository/managing-repository-settings/configuring-autolinks-to-reference-external-resources
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Repositories
shortTitle: Configurar links automáticos
---

## About autolinks

Qualquer pessoa com permissões de administrador para um repositório pode configurar referências de autolink para vincular problemas, pull requests, mensagens do commit e descrições de versões para serviços externos de terceiros.

{% ifversion autolink-reference-alphanumeric %}
Autolink references can now accept alphanumeric characters. When originally introduced, custom autolinks were limited to external resources that used numeric identifiers. Custom autolinks now work with alphanumeric identifiers. Legacy autolink references that recognize only numeric identifiers are deprecated and displayed with a "legacy" label.

You define custom autolinks by specifying a reference prefix and a target URL.
- Reference prefixes cannot have overlapping names. For example, a repository cannot have two custom autolinks with prefixes such as `TICKET` and `TICK`, since both prefixes would match the string `TICKET123a`.
- Target URLs include a `<num>` variable which supports the following characters: `a-z` (case-insensitive), `0-9`, and `-`.
{% endif %}

## Configurar links automáticos para fazer referência a recursos externos

This procedure demonstrates how to configure autolinks to reference external resources. For example, if you use Zendesk to track user-reported tickets, you can reference a ticket number in the pull request you opened to fix the issue.

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% ifversion fpt or ghec or ghes > 3.4 or ghae-issue-5658 %}
1. Na seção "Integrações" na barra lateral, clique em **Referências autolink de {% octicon "cross-reference" aria-label="The cross-reference icon" %}**.
{% else %}
1. Na barra lateral esquerda, clique em **Autolink references** (Referências de link automático). ![Guia Autolink references (Referências de link automático) na barra lateral esquerda](/assets/images/help/repository/autolink-references-tab.png)
{% endif %}
1. Clique em **Add autolink reference** (Adicionar referência de link automático). ![Botão para preencher informações de referência de link automático](/assets/images/help/repository/add-autolink-reference-details.png)
5. Em "Reference prefix" (Prefixo da referência), digite um prefixo curto e significativo que os colaboradores devem usar para gerar links automáticos para os recursos externos.
{% ifversion autolink-reference-alphanumeric %}![Field to type abbreviation for external system](/assets/images/help/repository/add-reference-prefix-field-alphanumeric.png){% else %}![Field to type abbreviation for external system](/assets/images/help/repository/add-reference-prefix-field.png){% endif %}
6. Em "Target URL" (URL de destino), digite o link para o sistema externo com o qual deseja criar vínculo. Certifique-se de manter `<num>` como uma variável para o número de referência.
{% ifversion autolink-reference-alphanumeric %}![Field to type URL to external system](/assets/images/help/repository/add-target-url-field-alphanumeric.png){% else %}![Field to type URL to external system](/assets/images/help/repository/add-target-url-field.png){% endif %}
7. Clique em **Add autolink reference** (Adicionar referência de link automático).
{% ifversion autolink-reference-alphanumeric %}{% else %}![Button to add autolink reference](/assets/images/help/repository/add-autolink-reference.png){% endif %}
