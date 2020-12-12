---
description: 'Dowiedz się więcej na temat: _InterlockedCompareExchangePointer funkcje wewnętrzne'
title: Funkcje wewnętrzne _InterlockedCompareExchangePointer
ms.date: 09/02/2019
f1_keywords:
- _InterlockedCompareExchangePointer_HLERelease
- _InterlockedCompareExchangePointer_rel
- _InterlockedCompareExchangePointer_acq_cpp
- _InterlockedCompareExchangePointer
- _InterlockedCompareExchangePointer_cpp
- _InterlockedCompareExchangePointer_np
- _InterlockedCompareExchangePointer_rel_cpp
- _InterlockedCompareExchangePointer_HLEAcquire
- _InterlockedCompareExchangePointer_acq
- _InterlockedCompareExchangePointer_nf
helpviewer_keywords:
- InterlockedCompareExchangePointer_acq intrinsic
- _InterlockedCompareExchangePointer_rel intrinsic
- _InterlockedCompareExchangePointer_acq intrinsic
- InterlockedCompareExchangePointer_rel intrinsic
- InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_HLERelease intrinsic
- _InterlockedCompareExchangePointer_HLEAcquire intrinsic
- _InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_nf intrinsic
- _InterlockedCompareExchangePointer_np intrinsic
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
ms.openlocfilehash: cd8d42c6a7036a6c779af6fc32a7176b7e48a73c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168062"
---
# <a name="_interlockedcompareexchangepointer-intrinsic-functions"></a>Funkcje wewnętrzne _InterlockedCompareExchangePointer

**Specyficzne dla firmy Microsoft**

Wykonuje niepodzielną operację, która przechowuje `Exchange` adres w `Destination` adresie, jeśli wartość `Comparand` i `Destination` adres są równe.

## <a name="syntax"></a>Składnia

```C
void * _InterlockedCompareExchangePointer (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_acq (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_HLEAcquire (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_HLERelease (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_nf (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_np (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
long _InterlockedCompareExchangePointer_rel (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
```

### <a name="parameters"></a>Parametry

*Punktu*\
[in. out] Wskaźnik na wskaźnik do wartości docelowej. Znak jest ignorowany.

*Exchange*\
podczas Wskaźnik programu Exchange. Znak jest ignorowany.

*Argument porównania określony*\
podczas Wskaźnik do porównania z miejscem docelowym. Znak jest ignorowany.

## <a name="return-value"></a>Wartość zwracana

Wartość zwracana jest początkową wartością miejsca docelowego.

## <a name="requirements"></a>Wymagania

|Wewnętrznej|Architektura|Nagłówek|
|---------------|------------------|------------|
|`_InterlockedCompareExchangePointer`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM, ARM64|\<iiintrin.h>|
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, x64|\<immintrin.h>|

## <a name="remarks"></a>Uwagi

`_InterlockedCompareExchangePointer` wykonuje niepodzielną porównanie `Destination` adresu z `Comparand` adresem. Jeśli `Destination` adres jest równy `Comparand` adresowi, `Exchange` adres jest przechowywany w adresie określonym przez `Destination` . W przeciwnym razie nie jest wykonywana żadna operacja.

`_InterlockedCompareExchangePointer` zapewnia wewnętrzną obsługę kompilatora dla funkcji [InterlockedCompareExchangePointer](/windows-hardware/drivers/ddi/content/wdm/nf-wdm-interlockedcompareexchangepointer) Win32 Windows SDK.

Przykład użycia programu można `_InterlockedCompareExchangePointer` znaleźć w temacie [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

Na platformach ARM Użyj funkcji wewnętrznych z `_acq` i `_rel` sufiksów, jeśli potrzebujesz uzyskiwania i wydawania semantyki, na przykład na początku i na końcu sekcji krytycznej. Elementy wewnętrzne ARM z `_nf` sufiksem ("No ogrodzeni") nie działają jako bariera pamięci.

Elementy wewnętrzne z `_np` sufiksem ("No Fetch") uniemożliwiają wstawienie przez kompilator możliwej operacji pobierania z wyprzedzeniem.

Na platformach firmy Intel, które obsługują instrukcje dotyczące blokowania sprzętowego dla koprocedury (HLE), wewnętrzne z `_HLEAcquire` i `_HLERelease` sufiksy zawierają wskazówkę do procesora, który może przyspieszyć działanie, eliminując krok blokady zapisu sprzętu. Jeśli te elementy wewnętrzne są wywoływane na platformach, które nie obsługują HLE, Wskazówka jest ignorowana.

Te procedury są dostępne tylko jako elementy wewnętrzne.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)
