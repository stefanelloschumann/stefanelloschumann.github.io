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

## 4. Checkbox

| **Ordem** | **Tipo** | **Descrição**      | **Valor default** |
| --------- | -------- | -------------      | ----------------- |
| 1         | Inteiro  | Tipo do campo      | 4                 |
| 2         | String   | Descrição do campo | ''                |
| 3         | Lógico   | Valor inicial      | 1                 |
| 4         | Array    | Texto do rótulo    | {}                |
| 4         | Inteiro  | Tamanho do campo   | 90                |
| 5         | String   | Validação          | ''                |
| 6         | Lógico   | Campo obrigatório  | .T.               |

## 2. ComboBox

| **Ordem** | **Tipo** | **Descrição**           | **Valor default** |
| --------- | -------- | -------------           | ----------------- |
| 1         | Inteiro  | Tipo do campo           | 2                 |
| 2         | String   | Descrição do campo      | ''                |
| 3         | Inteiro  | Índice do valor inicial | 1                 |
| 4         | Array    | Strings com as opções   | {}                |
| 5         | Inteiro  | Tamanho do campo        | 90                |
| 6         | String   | Validação               | ''                |
| 7         | Lógico   | Campo obrigatório       | .T.               |

## 6. Arquivo

| **Ordem** | **Tipo** | **Descrição**               | **Valor default**       |
| --------- | -------- | -------------               | -----------------       |
| 1         | Inteiro  | Tipo do campo               | 6                       |
| 2         | String   | Descrição do campo          | ''                      |
| 3         | String   | Incialização do campo       | ''                      |
| 4         | String   | Picture do campo            | ''                      |
| 5         | String   | Validação                   | ''                      |
| 6         | String   | Validação When              | ''                      |
| 7         | Inteiro  | Tamanho do campo            | 90                      |
| 8         | Lógico   | Campo obrigatório           | .T.                     |
| 9         | String   | Tipos de arquivo            | 'Arquivos .CSV | *.CSV' |
| 10        | String   | Diretório inicial           | '/'                     |
| 11        | String   | Tipo de visualização        | 128                     |
| 12        | Lógico   | Mostrar árvore do servidor  | 128                     |

| Tipos de visualização                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **2**   | *GETF_MULTISELECT*  | Permite selecionar mais de 1 arquivo no padrão "arquivo1 \| arquivo2 \| arquivo3". *Observação: Não compativel com o comando "GETF_RETDIRECTORY" e com a edição do "Nome do Arquivo".* |
| **4**   | *GETF_NOCHANGEDIR*  | Não permite mudar o diretório inicial.                                                                                                                                                 |
| **8**   | *GETF_LOCALFLOPPY*  | Apresenta a unidade do disquete da máquina local.                                                                                                                                      |
| **16**  | *GETF_LOCALHARD*    | Apresenta a unidade do disco local.                                                                                                                                                    |
| **32**  | *GETF_NETWORKDRIVE* | Apresenta as unidades da rede (mapeamento). Ao executar o SmartClient com um usuário diferente do usuário logado na sessão no Windows os drives de Rede não serão apresentados.        |
| **64**  | *GETF_SHAREWARE*    | Não implementado.                                                                                                                                                                      |
| **128** | *GETF_RETDIRECTORY* | Retorna/apresenta um diretório.                                                                                                                                                        |
| **256** | *GETF_HIDDENDIR*    | Mostra arquivos e pastas ocultas. *Observação: disponível em builds superiores a 7.00.131227A.*                                                                                        |
| **512** | *GETF_SYSDIR*       | Mostra arquivos e pastas do sistema. *Observação: disponível em builds superiores a 7.00.131227A.*                                                                                     | 