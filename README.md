# Kubuma — Sistema de Gestão Empresarial

**Estudo de caso técnico | ERP para operações de pequenas e médias empresas**

> **Showcase público:** este repositório apresenta o projecto e algumas decisões de engenharia. O código-fonte da aplicação é privado. A documentação foi elaborada a partir de uma análise estática de uma versão do código em Novembro de 2026; não constitui certificação de funcionamento em produção.

## Visão geral

O **Kubuma** é uma aplicação empresarial desenvolvida para centralizar processos de **gestão de stock, vendas e facturação, contabilidade, fiscalidade e recursos humanos**. A proposta é reduzir a fragmentação de informação operacional e financeira através de módulos integrados.

**Papel:** desenvolvimento full-stack do projecto (projecto apresentado por Alane Savanguane; contributos individuais detalhados e eventual equipa por confirmar).  
**Autor do showcase:** [Alane Savanguane](https://github.com/AlaneDeJesus258)  
**Estado:** projecto em desenvolvimento/evolução; demonstração pública ainda não disponibilizada.

## Tecnologias identificadas no código

| Camada | Ferramentas |
| --- | --- |
| Backend | PHP 8.3+, Laravel 13 |
| Interface | Laravel Blade, Tailwind CSS 4, Vite 8 |
| Autenticação e API | Laravel Jetstream e Sanctum (dependências presentes) |
| Persistência | Eloquent ORM e migrações Laravel; o motor de base de dados do ambiente de produção não foi validado |
| Exportação | DomPDF e templates de exportação PDF/Excel |
| Testes | Pest 4 (configurado; cobertura funcional ainda por desenvolver/verificar) |

## Áreas funcionais identificadas

- **Stock e inventário:** produtos, unidades, lotes e movimentações.
- **Vendas e facturação:** clientes, facturas, pagamentos e cancelamento de facturas.
- **Contabilidade:** plano de contas, lançamentos, balanços, demonstração de resultados e fluxos de caixa.
- **Fiscalidade:** fluxos de IVA, IRPS e INSS identificados no código.
- **Recursos humanos:** colaboradores, horários, assiduidade, processamento salarial e subsídios.
- **Organização empresarial:** empresas, utilizadores, períodos fiscais e relatórios.

*As áreas acima foram identificadas pela estrutura de classes, rotas, migrações e vistas; a existência do código não demonstra que cada fluxo esteja concluído ou validado em produção.*

## Decisões técnicas que o projecto evidencia

1. **Separação de responsabilidades:** a aplicação utiliza controladores e serviços especializados, como `InvoiceService` e `AccountingEventDispatcherService`.
2. **Operações transaccionais:** o código recorre a `DB::transaction()` em determinados processos de facturação e contabilidade.
3. **Registo de eventos contabilísticos:** existem mecanismos de processamento e registo de eventos, com identificadores de rastreio no serviço de despacho contabilístico.
4. **Gestão de contexto empresarial:** existe middleware para exigir a selecção de empresa em determinados fluxos.

Lê mais em [Arquitectura](docs/architecture.md) e [Decisões técnicas](docs/technical-decisions.md).

## Demonstração e evidências

| Evidência | Disponibilidade |
| --- | --- |
| Código-fonte | Privado |
| Capturas de ecrã | A adicionar, após revisão de dados e direitos |
| Demonstração em vídeo | A preparar |
| Instância de demonstração | Não publicada |
| Testes automatizados de negócio | Não demonstrados nesta versão |
| Documentação pública | Disponível neste repositório |

Para cada imagem ou vídeo publicado, serão utilizados **dados fictícios** e nenhuma informação confidencial de clientes.

## Documentação

- [Mapa de funcionalidades](docs/features.md)
- [Arquitectura técnica](docs/architecture.md)
- [Decisões de engenharia](docs/technical-decisions.md)
- [Plano de evidências para o portefólio](docs/evidence-plan.md)

## Privacidade e propriedade intelectual

Este repositório **não contém** o código-fonte, migrações, configurações internas, credenciais, bases de dados, chaves de API nem dados reais de clientes. Não é uma distribuição do software e não concede licença de utilização comercial.

## Contacto

**Alane Savanguane** · Maputo, Moçambique  
[GitHub](https://github.com/AlaneDeJesus258) · [Email](mailto:savanguanealane757@gmail.com)
