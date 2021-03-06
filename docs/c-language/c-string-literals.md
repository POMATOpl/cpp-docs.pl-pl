---
description: 'Dowiedz się więcej o: literały ciągu języka C'
title: Literały ciągu języka C
ms.date: 08/31/2018
helpviewer_keywords:
- string literals, syntax
- strings [C++], string literals
- literal strings, C
ms.assetid: 4b05523e-49a2-4900-b21a-754350af3328
ms.openlocfilehash: c18a13dcc44203399aa6518f53031d29b00a5a4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207088"
---
# <a name="c-string-literals"></a>Literały ciągu języka C

"Literał ciągu" to sekwencja znaków z zestawu znaków źródłowych ujęta w znaki podwójnego cudzysłowu (**""**). Literały ciągu są używane do reprezentowania sekwencji znaków, które razem tworzą ciąg zakończony znakiem null. Należy zawsze prefiksować literały o szerokim ciągu z literą **L**.

## <a name="syntax"></a>Składnia

*literał ciągu*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**"** *s-char-Sequence*<sub>opt</sub> **"**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**L "** *s-char-Sequence*<sub></sub> **"**

*s-char-Sequence*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*s-char*

&nbsp;&nbsp;&nbsp;&nbsp;*s-char-Sequence* *s-char*

*s-char*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Każdy element członkowski zestawu znaków źródłowych z wyjątkiem podwójnego cudzysłowu ("), ukośnika odwrotnego ( \\ ) lub znaku nowego wiersza

&nbsp;&nbsp;&nbsp;&nbsp;*Sekwencja ucieczki*

## <a name="remarks"></a>Uwagi

Poniższy przykład jest prostym literałem ciągu:

```C
char *amessage = "This is a string literal.";
```

Wszystkie kody ucieczki wymienione w tabeli [sequences Escape](../c-language/escape-sequences.md) są prawidłowe w literałach ciągu. Aby przedstawić podwójny cudzysłów w literale ciągu, użyj sekwencji unikowej **\\ "**. Znak pojedynczego cudzysłowu (**'**) może być reprezentowany bez sekwencji ucieczki. Po znaku ukośnika odwrotnego ( **\\** ) musi następować drugi ukośnik odwrotny ( **\\\\** ), gdy występuje w ciągu. Gdy ukośnik odwrotny pojawia się na końcu wiersza, jest zawsze interpretowany jako znak kontynuacji wiersza.

## <a name="see-also"></a>Zobacz też

[Elementy języka C](../c-language/elements-of-c.md)
