---
categories: AdvPL Protheus Totvs ParamBox
author:     Eduardo Stefanello
title:      Utilizando o ParamBox
date:       2021-10-11 13:52:49 -0300
layout:     post
---
**ParamBox** é uma função do *Protheus* para uma caixa de diálogo para passagem de parâmetros.

Os parâmetros dessa função são: Um *array* com as opções da caixa de diálogo e a referência de um *array* para o retorno das opções que o usuário selecionar.

A função Parambox retorna um valor lógico, que possibilita que ela seja usada como expressão lógica em um if.

O *array* de opções começa com o tipo do campo. Abaixo os tipos possíveis:

***

## 1. Data

| **Ordem** | **Tipo** | **Descrição**          | **Valor default** |
| --------- | -------- | -------------          | ----------------- |
| 1         | Inteiro  | Tipo do campo          | `1`               |
| 2         | String   | Descricao              | `''`              |
| 3         | String   | Valor inicial do campo | `''`              |
| 4         | String   | Picture do campo       | `''`              |
| 5         | String   | Validacao do campo     | `''`              |
| 6         | String   | Consulta F3            | `''`              |
| 7         | String   | Validacao When         | `''`              |
| 8         | Inteiro  | Tamanho do campo       | `90`              |
| 9         | Lógico   | Parametro Obrigatorio  | `.T`              |

## 2. ComboBox

| **Ordem** | **Tipo** | **Descrição**          | **Valor default** |
| --------- | -------- | -------------          | ----------------- |
| 1         | Inteiro  | Tipo do campo          | `2`               |
| 2         | String   | Descrição do campo     | `''`              |
| 3         | String   | Valor inicial do campo | `''`              |
| 4         | Array    | Strings com as opções  | `{}`              |
| 5         | Inteiro  | Tamanho do campo       | `90`              |
| 6         | String   | Validação              | `''`              |
| 7         | Lógico   | Campo obrigatório      | `.T.`             |

## 3. Radio

| **Ordem** | **Tipo** | **Descrição**          | **Valor default** |
| --------- | -------- | -------------          | ----------------- |
| 1         | Inteiro  | Tipo do campo          | `4`               |
| 2         | String   | Descrição do campo     | `''`              |
| 3         | Inteiro  | Valor inicial do campo | `1`               |
| 4         | Array    | Strings com as opções  | `{}`              |
| 5         | Inteiro  | Tamanho do campo       | `90`              |
| 6         | String   | Validação              | `''`              |
| 7         | Lógico   | Campo obrigatório      | `.T.`             |

## 4. Checkbox com descrição

| **Ordem** | **Tipo** | **Descrição**      | **Valor default** |
| --------- | -------- | -------------      | ----------------- |
| 1         | Inteiro  | Tipo do campo      | `4`               |
| 2         | String   | Descrição do campo | `''`              |
| 3         | Lógico   | Valor inicial      | `1`               |
| 4         | String   | Texto do rótulo    | `''`              |
| 5         | Inteiro  | Tamanho do campo   | `90`              |
| 6         | String   | Validação          | `''`              |
| 7         | Lógico   | Campo obrigatório  | `.T.`             |

## 4. Checkbox

| **Ordem** | **Tipo** | **Descrição**      | **Valor default** |
| --------- | -------- | -------------      | ----------------- |
| 1         | Inteiro  | Tipo do campo      | `4`               |
| 2         | String   | Descrição do campo | `''`              |
| 3         | Lógico   | Valor inicial      | `1`               |
| 4         | Inteiro  | Tamanho do campo   | `90`              |
| 5         | String   | Validação          | `''`              |
| 6         | Lógico   | Campo obrigatório  | `.T.`             |

## 6. Arquivo

| **Ordem** | **Tipo** | **Descrição**               | **Valor default**          |
| --------- | -------- | -------------               | -----------------          |
| 1         | Inteiro  | Tipo do campo               | `6`                        |
| 2         | String   | Descrição do campo          | `''`                       |
| 3         | String   | Incialização do campo       | `''`                       |
| 4         | String   | Picture do campo            | `''`                       |
| 5         | String   | Validação                   | `''`                       |
| 6         | String   | Validação When              | `''`                       |
| 7         | Inteiro  | Tamanho do campo            | `90`                       |
| 8         | Lógico   | Campo obrigatório           | `.T.`                      |
| 9         | String   | Tipos de arquivo            | `'Arquivos .CSV \| *.CSV'` |
| 10        | String   | Diretório inicial           | `'/'`                      |
| 11        | String   | Tipo de visualização        | `128`                      |
| 12        | Lógico   | Mostrar árvore do servidor  | `.F.`                      |

### Tipos de visualização

| **2**   | *GETF_MULTISELECT*  | Permite selecionar mais de 1 arquivo no padrão "arquivo1 \| arquivo2 \| arquivo3". *Observação: Não compativel com o comando "GETF_RETDIRECTORY" e com a edição do "Nome do Arquivo".* |
| **4**   | *GETF_NOCHANGEDIR*  | Não permite mudar o diretório inicial.                                                                                                                                                 |
| **8**   | *GETF_LOCALFLOPPY*  | Apresenta a unidade do disquete da máquina local.                                                                                                                                      |
| **16**  | *GETF_LOCALHARD*    | Apresenta a unidade do disco local.                                                                                                                                                    |
| **32**  | *GETF_NETWORKDRIVE* | Apresenta as unidades da rede (mapeamento). Ao executar o SmartClient com um usuário diferente do usuário logado na sessão no Windows os drives de Rede não serão apresentados.        |
| **64**  | *GETF_SHAREWARE*    | Não implementado.                                                                                                                                                                      |
| **128** | *GETF_RETDIRECTORY* | Retorna/apresenta um diretório.                                                                                                                                                        |
| **256** | *GETF_HIDDENDIR*    | Mostra arquivos e pastas ocultas. *Observação: disponível em builds superiores a 7.00.131227A.*                                                                                        |
| **512** | *GETF_SYSDIR*       | Mostra arquivos e pastas do sistema. *Observação: disponível em builds superiores a 7.00.131227A.*                                                                                     | 

## 7. Expressão de filtro

| **Ordem** | **Tipo** | **Descrição**      | **Valor default** |
| --------- | -------- | -------------      | ----------------- |
| 1         | Inteiro  | Tipo do campo      | `7`               |
| 2         | String   | Descrição do campo | `''`              |
| 3         | String   | Alias da tabela    | `''`              |
| 4         | Lógico   | Filtro inicial     | `1`               |

## 8. Senha

| **Ordem** | **Tipo** | **Descrição**          | **Valor default** |
| --------- | -------- | -------------          | ----------------- |
| 1         | Inteiro  | Tipo do campo          | `8`               |
| 2         | String   | Descricao              | `''`              |
| 3         | String   | Valor inicial do campo | `''`              |
| 4         | String   | Picture do campo       | `''`              |
| 5         | String   | Validacao do campo     | `''`              |
| 6         | String   | Consulta F3            | `''`              |
| 7         | String   | Validação When         | `''`              |
| 8         | Inteiro  | Tamanho do campo       | `90`              |
| 9         | Lógico   | Parametro Obrigatorio  | `.T`              |

## 9. Label

| **Ordem** | **Tipo** | **Descrição**         | **Valor default** |
| --------- | -------- | -------------         | ----------------- |
| 1         | Inteiro  | Tipo do campo         | `9`               |
| 2         | String   | Descrição do campo    | `''`              |
| 3         | Inteiro  | Largura da *label*    | `''`              |
| 3         | Inteiro  | Altura da *label*     | `''`              |
| 4         | Lógico   | Parametro obrigatorio | `1`               |

## 10. Range

| **Ordem** | **Tipo** | **Descrição**          | **Valor default** |
| --------- | -------- | -------------          | ----------------- |
| 1         | Inteiro  | Tipo do campo          | `10`              |
| 2         | String   | Descricao              | `''`              |
| 3         | String   | Valor inicial do campo | `''`              |
| 4         | String   | Consulta F3            | `''`              |
| 5         | Inteiro  | Tamanho do campo       | `90`              |
| 6         | String   | Tipo do campo (D ou C) | `''`              |
| 7         | Inteiro  | Passo                  | `5`               |
| 8         | String   | Validação When         | `''`              |

## 11. Memo

| **Ordem** | **Tipo** | **Descrição**          | **Valor default** |
| --------- | -------- | -------------          | ----------------- |
| 1         | Inteiro  | Tipo do campo          | `11`              |
| 2         | String   | Descricao              | `''`              |
| 3         | String   | Valor inicial do campo | `''`              |
| 4         | String   | Validacao do campo     | `''`              |
| 5         | String   | Validacao When         | `''`              |
| 6         | Lógico   | Parametro Obrigatorio  | `.T`              |

***

## Assinatura do ParamBox

| **Ordem** | **Nome**      | **Descrição**                                            | **Valor default** |
| --------- | --------      | -------------                                            | ----------------- |
| **1**     | *aParametros* | Vetor com as configurações                               |                   |
| **2**     | *cTitle*      | Título da janela                                         |                   |
| **3**     | *aRet*        | Referencia de vetor que contém o retorno dos parâmetros  |                   |
| **4**     | *bOk*         | Code block para validar o botão Ok                       | `bOk`             | 
| **5**     | *aButtons*    | Vetor com mais botões além dos botões de *Ok* e *Cancel* | `aButtons`        | 
| **6**     | *lCentered*   | Centralizar a janela                                     | `lCentered`       | 
| **7**     | *nPosX*       | Se não centralizar janela coordenada X para início       | `nPosX`           | 
| **8**     | *nPosY*       | Se não centralizar janela coordenada Y para início       | `nPosY`           | 
| **9**     | *oDlgWizard*  | Utiliza o objeto da janela ativa                         |                   |
| **10**    | *cLoad*       | Nome do perfil se caso for carregar                      | `cLoad`           | 
| **11**    | *lCanSave*    | Salvar os dados informados nos parâmetros por perfil     | `lCanSave`        | 
| **12**    | *lUserSave*   | Configuração por usuário                                 | `lUserSave`       | 

***

#### Referências:

[BlackTDN - Desvendando a Função ParamBox](http://www.blacktdn.com.br/2012/05/para-quem-precisar-desenvolver-uma.html)