---
description: 'Dowiedz się więcej na temat: Klasa DontUseNewUseMake'
title: DontUseNewUseMake — Klasa
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
ms.openlocfilehash: f6b6740e472123e59565e3bad16e4a535a4e17fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272906"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake — Klasa

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Uwagi

Uniemożliwia używanie operatora `new` w `RuntimeClass` . W związku z tym należy zamiast tego użyć [funkcji Make](make-function.md) .

## <a name="members"></a>Elementy członkowskie

### <a name="public-operators"></a>Operatory publiczne

Nazwa                                             | Opis
------------------------------------------------ | ---------------------------------------------------------------------------
[DontUseNewUseMake:: operator new](#operator-new) | Operator overloads `new` i uniemożliwia używanie go w programie `RuntimeClass` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`DontUseNewUseMake`

## <a name="requirements"></a>Wymagania

**Nagłówek:** implementuje. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="dontusenewusemakeoperator-new"></a><a name="operator-new"></a> DontUseNewUseMake:: operator new

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Parametry

*__unnamed0*<br/>
Nienazwany parametr, który określa liczbę bajtów pamięci do przydzielenia.

*jęcia*<br/>
Typ do przydzielenia.

### <a name="return-value"></a>Wartość zwracana

Zapewnia sposób przekazania dodatkowych argumentów w przypadku przeciążania operatora `new` .

### <a name="remarks"></a>Uwagi

Operator overloads `new` i uniemożliwia używanie go w programie `RuntimeClass` .
