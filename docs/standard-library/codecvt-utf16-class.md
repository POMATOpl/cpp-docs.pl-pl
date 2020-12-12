---
description: 'Dowiedz się więcej na temat: codecvt_utf16'
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: 264324d0f827e8999b065205010874ebf62ca501
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325091"
---
# <a name="codecvt_utf16"></a>codecvt_utf16

Reprezentuje zestaw reguł [ustawień regionalnych](../standard-library/locale-class.md) , który konwertuje między znaki szerokie kodowane jako UCS-2 lub UCS-4 i strumień bajtów zakodowany jako UTF-16LE lub UTF-16BE.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametry

*Elem*\
Typ elementu dwubajtowego.

*Maxcode*\
Maksymalna liczba znaków dla zestawu reguł ustawień regionalnych.

*Wyst*\
Informacje o konfiguracji zestawu reguł ustawień regionalnych.

## <a name="remarks"></a>Uwagi

Ten szablon klasy wykonuje konwersję między znakami dwubajtowymi zakodowanymi jako UCS-2 lub UCS-4 i zakodowaną strumieniowo jako UTF-16LE, jeśli tryb & little_endian lub UTF-16BE w inny sposób.

Strumień bajtów powinien być zapisany w pliku binarnym; może być uszkodzona, jeśli Zapisano w pliku tekstowym.

## <a name="requirements"></a>Wymagania

Nagłówki \<codecvt>

Przestrzeń nazw: std
