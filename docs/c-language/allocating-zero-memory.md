---
description: 'Dowiedz się więcej o programie: przydzielanie zerowej pamięci'
title: Przydzielanie pamięci zerowej
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: 7971d9e097d00607af2acf4590ff3daaf67f7127
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280147"
---
# <a name="allocating-zero-memory"></a>Przydzielanie pamięci zerowej

**4.10.3 ANSI** Zachowanie `calloc` `malloc` funkcji,, lub, `realloc` Jeśli żądany rozmiar wynosi zero

`calloc`Funkcje, `malloc` i `realloc` akceptują zero jako argument. Nie przydzielono rzeczywistej pamięci, ale zwracany jest prawidłowy wskaźnik, a blok pamięci może być później modyfikowany przez ponowne alokację.

## <a name="see-also"></a>Zobacz też

[Funkcje biblioteki](../c-language/library-functions.md)
