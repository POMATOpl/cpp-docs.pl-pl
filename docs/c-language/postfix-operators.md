---
description: 'Dowiedz się więcej na temat: operatory przyrostkowe'
title: Operatory przyrostka
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
ms.openlocfilehash: be8e7354d512174a4ab11ffcdcb82f9418baa894
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195869"
---
# <a name="postfix-operators"></a>Operatory przyrostka

Operatory przyrostkowe mają najwyższy priorytet (najściślejsze wiązanie) podczas obliczania wyrażenia.

## <a name="syntax"></a>Składnia

*wyrażenie przyrostkowe*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie podstawowe*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*przyrostk — wyrażenie*  **[**  *wyrażenie*  **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*przyrostkowe wyrażenie***(***opt-expression-list*<sub></sub> **)**    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie przyrostkowe*  **.**  *identyfikatora*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie* **->** przyrostkowe *Identyfikator*    <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie przyrostkowe*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie przyrostkowe*  **--**

Operatory na tym poziomie pierwszeństwa są indeksami dolnymi tablicy, wywołaniami funkcji, strukturą i elementami członkowskimi Unii oraz przyrostem przyrostkowym i zmniejszeniem.

## <a name="see-also"></a>Zobacz też

[Operatory języka C](../c-language/c-operators.md)
