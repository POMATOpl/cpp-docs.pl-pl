---
description: 'Dowiedz się więcej na temat: Omówienie instrukcji języka C'
title: Przegląd instrukcji C
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
ms.openlocfilehash: d2d6e7161f63e8508cb7e94d28b7bbafe44146e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243175"
---
# <a name="overview-of-c-statements"></a>Przegląd instrukcji C

Instrukcje języka C składają się z tokenów, wyrażeń i innych instrukcji. Instrukcja, która tworzy składnik innej instrukcji, nosi nazwę "Body" otaczającej instrukcji. Każdy typ instrukcji określony przez następującą składnię został omówiony w tej sekcji.

## <a name="syntax"></a>Składnia

*instrukcja*: [labeled-Statement](../c-language/goto-and-labeled-statements-c.md)

[instrukcja złożona](../c-language/compound-statement-c.md)

[Expression — instrukcja](../c-language/expression-statement-c.md)

[SELECT — instrukcja](../c-language/if-statement-c.md)

[iteracja — instrukcja](../c-language/do-while-statement-c.md)

[skoku — instrukcja](../c-language/break-statement-c.md)

[try-except-Statement](../c-language/try-except-statement-c.md) /* specyficzne dla firmy Microsoft \*/

[try-finally-Statement](../c-language/try-finally-statement-c.md)  / \* Specyficzne dla firmy Microsoft\*/

Często treść instrukcji to "złożona instrukcja". Złożona instrukcja składa się z innych instrukcji, które mogą zawierać słowa kluczowe. Złożona instrukcja jest rozdzielana nawiasami klamrowymi (**{}**). Wszystkie inne instrukcje języka C kończą się średnikiem (**;**). Średnik jest terminatorem instrukcji.

Instrukcja Expression zawiera wyrażenie C, które może zawierać operatory arytmetyczne lub logiczne wprowadzone w [wyrażeniach i przypisaniach](../c-language/expressions-and-assignments.md). Instrukcja o wartości null jest pustą instrukcją.

Każda instrukcja języka C może rozpoczynać się od etykiety identyfikującej składającej się z nazwy i dwukropka. Ponieważ tylko **`goto`** instrukcja rozpoznaje etykiety instrukcji, etykiety instrukcji są omawiane z **`goto`** . Aby uzyskać więcej informacji [, zobacz instrukcje goto i labeled](../c-language/goto-and-labeled-statements-c.md) .

## <a name="see-also"></a>Zobacz też

[Instrukcje](../c-language/statements-c.md)
