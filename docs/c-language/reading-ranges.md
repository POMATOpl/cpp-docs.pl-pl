---
description: 'Dowiedz się więcej na temat: odczytywanie zakresów'
title: Odczytywanie zakresów
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: afb1ff0f25360de7c47663279bf6f54dd7ca6a48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309124"
---
# <a name="reading-ranges"></a>Odczytywanie zakresów

**4.9.6.2 ANSI** Interpretacja znaku kreski (-), który nie jest pierwszym ani ostatnim znakiem w scanlist dla% [konwersja w `fscanf` funkcji

Poniższy wiersz

```
fscanf( fileptr, "%[A-Z]", strptr);
```

odczytuje dowolną liczbę znaków z zakresu od A do Z do ciągu, do którego `strptr` punkty.

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki](../c-language/library-functions.md)
