---
description: 'Dowiedz się więcej o usłudze: stałe plików'
title: Plik — Stałe
ms.date: 11/04/2016
f1_keywords:
- _O_EXCL
- _O_RDWR
- _O_APPEND
- _O_RDONLY
- _O_TRUNC
- _O_CREAT
- _O_WRONLY
helpviewer_keywords:
- _O_RDWR constant
- O_EXCL constant
- O_RDWR constant
- O_WRONLY constant
- O_APPEND constant
- O_CREAT constant
- _O_CREAT constant
- _O_APPEND constant
- _O_EXCL constant
- O_TRUNC constant
- _O_RDONLY constant
- _O_TRUNC constant
- O_RDONLY constant
- _O_WRONLY constant
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
ms.openlocfilehash: a174a9bd8924f4d209f937187614863ce7111b3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296605"
---
# <a name="file-constants"></a>Plik — Stałe

## <a name="syntax"></a>Składnia

```
#include <fcntl.h>
```

## <a name="remarks"></a>Uwagi

Wyrażenie liczby całkowitej utworzone z co najmniej jednej z tych stałych określa typ dozwolonych operacji odczytu lub zapisu. Jest on tworzony przez połączenie jednej lub więcej stałych z stałą trybu tłumaczenia.

Stałe plików są następujące:

|Stała|Opis|
|-|-|
| `_O_APPEND`  | Zmienia położenie wskaźnika pliku na koniec pliku przed każdą operacją zapisu.  |
| `_O_CREAT`  | Tworzy i otwiera nowy plik do zapisu; nie ma to żadnego efektu, jeśli istnieje plik określony przez *filename* .  |
| `_O_EXCL`  | Zwraca wartość błędu, jeśli istnieje plik określony przez *nazwę* pliku. Stosuje się tylko w przypadku użycia z `_O_CREAT` .  |
| `_O_RDONLY`  | Otwiera plik tylko do odczytu; Jeśli ta flaga jest określona, nie `_O_RDWR` można ani nie `_O_WRONLY` może zostać określona.  |
| `_O_RDWR`  | Otwiera plik do odczytu i zapisu; Jeśli ta flaga jest określona, nie `_O_RDONLY` można ani nie `_O_WRONLY` może zostać określona.  |
| `_O_TRUNC`  | Otwiera i obcina istniejący plik o zerowej długości; plik musi mieć uprawnienia do zapisu. Zawartość pliku została zniszczona. Jeśli ta flaga jest podana, nie można określić `_O_RDONLY` .  |
| `_O_WRONLY`  | Otwiera plik tylko do zapisu; Jeśli ta flaga jest określona, nie `_O_RDONLY` można ani nie `_O_RDWR` może zostać określona.  |

## <a name="see-also"></a>Zobacz też

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[Stałe globalne](../c-runtime-library/global-constants.md)
