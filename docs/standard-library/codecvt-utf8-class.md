---
description: 'Dowiedz się więcej na temat: codecvt_utf8'
title: codecvt_utf8
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf8
helpviewer_keywords:
- codecvt_utf8 class
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
ms.openlocfilehash: b0da37607d563786285564d17b2c8a49e9e064bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234036"
---
# <a name="codecvt_utf8"></a>codecvt_utf8

Reprezentuje zestaw reguł [ustawień regionalnych](../standard-library/locale-class.md) , który konwertuje między znaki szerokie kodowane jako UCS-2 lub UCS-4, oraz strumień bajtów zakodowany jako UTF-8.

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>Parametry

*Elem*\
Typ elementu dwubajtowego.

*Maxcode*\
Maksymalna liczba znaków dla zestawu reguł ustawień regionalnych.

*Wyst*\
Informacje o konfiguracji zestawu reguł ustawień regionalnych.

## <a name="remarks"></a>Uwagi

Strumień bajtów można zapisać w pliku binarnym lub pliku tekstowym.

## <a name="requirements"></a>Wymagania

Nagłówki \<codecvt>

Przestrzeń nazw: std
