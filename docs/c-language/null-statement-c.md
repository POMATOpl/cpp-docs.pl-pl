---
description: 'Dowiedz się więcej na temat: o wartości null (C)'
title: Instrukcja o wartości Null (C)
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
ms.openlocfilehash: 362fc9e311d0495e0a3ab51da7a5042574859649
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243292"
---
# <a name="null-statement-c"></a>Instrukcja o wartości Null (C)

"Instrukcja o wartości null" jest instrukcją zawierającą tylko średnik; może pojawić się wszędzie tam, gdzie jest oczekiwana instrukcja. Nic się nie dzieje, gdy zostanie wykonana instrukcja o wartości null. Prawidłowym sposobem kodu instrukcji null jest:

## <a name="syntax"></a>Składnia

> **;**

## <a name="remarks"></a>Uwagi

Instrukcje, takie jak **`do`** ,, **`for`** **`if`** i **`while`** wymagają, aby instrukcja wykonywalna była wyświetlana jako treść instrukcji. Instrukcja o wartości null spełnia wymagania składniowe w przypadkach, w których nie jest wymagana treść instrukcji merytorycznej.

Podobnie jak w przypadku każdej innej instrukcji języka C, można dołączyć etykietę przed instrukcją o wartości null. Aby oznaczyć element, który nie jest instrukcją, taką jak zamykający nawias klamrowy instrukcji złożonej, można dodać etykietę do instrukcji null i wstawić ją bezpośrednio przed elementem, aby uzyskać ten sam efekt.

Ten przykład ilustruje instrukcję o wartości null:

```C
for ( i = 0; i < 10; line[i++] = 0 )
     ;
```

W tym przykładzie wyrażenie pętli **`for`** instrukcji `line[i++] = 0` inicjuje pierwsze 10 elementów od `line` do 0. Treść instrukcji jest instrukcją o wartości null, ponieważ dalsze instrukcje nie są wymagane.

## <a name="see-also"></a>Zobacz też

[Instrukcje](../c-language/statements-c.md)
