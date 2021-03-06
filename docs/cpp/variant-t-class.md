---
description: Dowiedz się więcej na temat klasy _variant_t
title: _variant_t — Klasa
ms.date: 11/04/2016
f1_keywords:
- _variant_t
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
ms.openlocfilehash: e720d78e6f7fd22fc369d4b39804260892e235c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116616"
---
# <a name="_variant_t-class"></a>_variant_t — Klasa

**Specyficzne dla firmy Microsoft**

Obiekt **_variant_t** hermetyzuje `VARIANT` Typ danych. Klasa zarządza alokacją zasobów i cofaniem alokacji i wykonuje wywołania funkcji do `VariantInit` i `VariantClear` w razie potrzeby.

### <a name="construction"></a>Budownictwo

| Nazwa | Opis |
|--|--|
| [_variant_t](../cpp/variant-t-variant-t.md) | Konstruuje obiekt **_variant_t** . |

### <a name="operations"></a>Operacje

| Nazwa | Opis |
|--|--|
| [Dołącz](../cpp/variant-t-attach.md) | Dołącza `VARIANT` obiekt do obiektu **_variant_t** . |
| [Czyste](../cpp/variant-t-clear.md) | Czyści obiekt hermetyzowany `VARIANT` . |
| [ChangeType](../cpp/variant-t-changetype.md) | Zmienia typ obiektu **_variant_t** na wskazany `VARTYPE` . |
| [Odłącz](../cpp/variant-t-detach.md) | Odłącza obiekt hermetyzowany `VARIANT` z tego obiektu **_variant_t** . |
| [Metodami SetString](../cpp/variant-t-setstring.md) | Przypisuje ciąg do tego obiektu **_variant_t** . |

### <a name="operators"></a>Operatory

| Nazwa | Opis |
|--|--|
| [Operator =](../cpp/variant-t-operator-equal.md) | Przypisuje nową wartość do istniejącego obiektu **_variant_t** . |
| [operator = =,! =](../cpp/variant-t-relational-operators.md) | Porównaj dwa **_variant_t** obiekty pod kątem równości lub nierówności. |
| [Ekstraktory](../cpp/variant-t-extractors.md) | Wyodrębnij dane z hermetyzowanego `VARIANT` obiektu. |

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<comutil.h>

**Lib:** comsuppw. lib lub comsuppwd. lib (patrz [/Zc: Wchar_t (Wchar_t jest typem natywnym)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) , aby uzyskać więcej informacji.

## <a name="see-also"></a>Zobacz też

[Klasy obsługi kompilatora COM](../cpp/compiler-com-support-classes.md)
