---
description: 'Dowiedz się więcej na temat: __unaligned'
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: f5afd0c6c1a506cbaeb03d497e64eac743ecc4df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145759"
---
# <a name="__unaligned"></a>__unaligned

**Specyficzne dla firmy Microsoft**. Gdy deklarujesz wskaźnik z **`__unaligned`** modyfikatorem, kompilator zakłada, że wskaźnik adresuje dane, które nie są wyrównane. W związku z tym jest generowany kod odpowiedni dla platformy w celu obsługi niewyrównanych odczytów i zapisów za pomocą wskaźnika.

## <a name="remarks"></a>Uwagi

Ten modyfikator opisuje wyrównanie danych rozmieszczonych przez wskaźnik; przyjmuje się, że sam wskaźnik jest wyrównany.

Konieczność **`__unaligned`** słowa kluczowego zależy od platformy i środowiska. Niepowodzenie oznaczania danych może spowodować problemy z wydajnością przed awariami sprzętowymi. **`__unaligned`** Modyfikator jest nieprawidłowy dla platformy x86.

W celu zapewnienia zgodności z poprzednimi wersjami, **`_unaligned`** jest synonimem, **`__unaligned`** Jeśli opcja kompilatora [ `/Za` \( disable rozszerzenia języka](../build/reference/za-ze-disable-language-extensions.md) nie jest określona.

Aby uzyskać więcej informacji na temat wyrównania, zobacz:

- [`align`](../cpp/align-cpp.md)

- [`alignof` Zakład](../cpp/alignof-operator.md)

- [`pack`](../preprocessor/pack.md)

- [`/Zp` (Wyrównanie składowej struktury)](../build/reference/zp-struct-member-alignment.md)

- [Przykłady wyrównania struktury](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>Zobacz też

[Słowa kluczowe](../cpp/keywords-cpp.md)
