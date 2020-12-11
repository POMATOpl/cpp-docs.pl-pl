---
description: 'Dowiedz się więcej na temat: _variant_t Extracts'
title: _variant_t — Ekstraktory
ms.date: 11/04/2016
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
ms.openlocfilehash: 55a02fdf422388b0e44a9aad77e86f7a76e80e3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161601"
---
# <a name="_variant_t-extractors"></a>_variant_t — Ekstraktory

**Specyficzne dla firmy Microsoft**

Wyodrębnij dane z hermetyzowanego `VARIANT` obiektu.

## <a name="syntax"></a>Składnia

```
operator short( ) const;
operator long( ) const;
operator float( ) const;
operator double( ) const;
operator CY( ) const;
operator _bstr_t( ) const;
operator IDispatch*( ) const;
operator bool( ) const;
operator IUnknown*( ) const;
operator DECIMAL( ) const;
operator BYTE( ) const;
operator VARIANT() const throw();
operator char() const;
operator unsigned short() const;
operator unsigned long() const;
operator int() const;
operator unsigned int() const;
operator __int64() const;
operator unsigned __int64() const;
```

## <a name="remarks"></a>Uwagi

Wyodrębnia pierwotne dane z hermetyzowania `VARIANT` . Jeśli `VARIANT` Typ nie jest jeszcze prawidłowy, `VariantChangeType` jest używany do próby konwersji, a w przypadku niepowodzenia zostanie wygenerowany błąd:

- **operator short ()** Wyodrębnia liczbę **`short`** całkowitą.

- **Długość operatora ()** Wyodrębnia liczbę **`long`** całkowitą.

- **zmiennoprzecinkowy operatora ()** Wyodrębnia **`float`** wartość liczbową.

- **operator Double ()** Wyodrębnia liczbę **`double`** całkowitą.

- **operator cy ()** Wyodrębnia `CY` obiekt.

- wartość **logiczna operatora ()** Wyodrębnia **`bool`** wartość.

- **liczba dziesiętna operatora ()** Wyodrębnia `DECIMAL` wartość.

- **bajt operatora ()** Wyodrębnia `BYTE` wartość.

- **_bstr_t operatora ()** Wyodrębnia ciąg, który jest hermetyzowany w `_bstr_t` obiekcie.

- **operator IDispatch \* ()** wyodrębnia wskaźnik dispinterface z hermetyzowania `VARIANT` . `AddRef` jest wywoływana na wskaźniku będącym wynikiem, aby można było go wywoływać `Release` .

- **operator IUnknown \* ()** WYODRĘBNIA wskaźnik interfejsu com z hermetyzowania `VARIANT` . `AddRef` jest wywoływana na wskaźniku będącym wynikiem, aby można było go wywoływać `Release` .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _variant_t](../cpp/variant-t-class.md)
