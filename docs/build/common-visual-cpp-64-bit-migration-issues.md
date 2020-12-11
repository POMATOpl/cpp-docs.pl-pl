---
description: 'Dowiedz się więcej o programie: typowe Visual C++ 64-bitowe problemy z migracją'
title: Typowe problemy przy migracji Visual C++ w wersji 64-bitowej
ms.date: 05/06/2019
helpviewer_keywords:
- 64-bit programming [C++], migration
- 64-bit compiler [C++], migration
- porting 32-bit code to 64-bit code
- migration [C++], 64-bit code issues
- 32-bit code porting [C++]
- 64-bit applications [C++]
- 64-bit compiler [C++], porting 32-bit code
- Win64 [C++]
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
ms.openlocfilehash: 86c4618423353a3a7ac217432ce9dfcb0c19061b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156895"
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Typowe problemy przy migracji Visual C++ w wersji 64-bitowej

W przypadku używania kompilatora języka Microsoft C++ (MSVC) do tworzenia aplikacji do uruchamiania w 64-bitowym systemie operacyjnym Windows należy pamiętać o następujących kwestiach:

- **`int`** A i a **`long`** są 32-bitowe wartości w 64-bitowych systemach operacyjnych Windows. W przypadku programów, które mają zostać skompilowane dla platform 64-bitowych, należy uważać, aby nie przypisywać wskaźników do zmiennych 32-bitowych. Wskaźniki są 64-bitowe na platformach 64-bitowych, a wartość wskaźnika zostanie obcinana, jeśli zostanie przypisana do zmiennej 32-bitowej.

- `size_t`, `time_t` i `ptrdiff_t` są 64-bitowe wartości w 64-bitowych systemach operacyjnych Windows.

- `time_t` to 32-bitowa wartość w 32-bitowych systemach operacyjnych Windows w programie Visual Studio 2005 i starszych. `time_t` jest teraz domyślnie 64-bitową liczbą całkowitą. Aby uzyskać więcej informacji, zobacz [Zarządzanie czasem](../c-runtime-library/time-management.md).

   Należy pamiętać, gdzie kod pobiera **`int`** wartość i przetwarza ją jako `size_t` `time_t` wartość. Możliwe, że liczba może wzrosnąć do wartości większej niż 32-bitowa, a dane zostaną obcięte, gdy zostanie przeniesiona z powrotem do **`int`** magazynu.

Modyfikator% x (szesnastkowo **`int`** Format) `printf` nie będzie działać zgodnie z oczekiwaniami w 64-bitowym systemie operacyjnym Windows. Będzie działać tylko w przypadku pierwszych 32 bitów wartości, która jest przenoszona do niej.

- Użyj elementu% I32x, aby wyświetlić 32-bitowy typ całkowity w formacie szesnastkowym.

- Użyj elementu% I64x, aby wyświetlić 64-bitowy typ całkowity w formacie szesnastkowym.

- % P (format szesnastkowy wskaźnika) będzie działać zgodnie z oczekiwaniami w 64-bitowym systemie operacyjnym Windows.

Aby uzyskać więcej informacji, zobacz:

- [Opcje kompilatora MSVC](reference/compiler-options.md)

- [Wskazówki dotyczące migracji](/windows/win32/WinProg64/migration-tips)

## <a name="see-also"></a>Zobacz też

[Konfigurowanie projektów C++ dla 64-bitowych, docelowych procesorów x64](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Przewodnik po przenoszeniu i uaktualnianiu pakietu Visual C++](../porting/visual-cpp-porting-and-upgrading-guide.md)
