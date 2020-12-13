---
description: Dowiedz się więcej na temat struktury space_info
title: space_info — Struktura
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::space_info
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
ms.openlocfilehash: 254866a0eb225b4ed7bcfe4e06a734c5c9d0e3ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153879"
---
# <a name="space_info-structure"></a>space_info — Struktura

Zawiera informacje o woluminie.

## <a name="syntax"></a>Składnia

```cpp
struct space_info
{
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
};
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|`unsigned long long capacity`|Reprezentuje łączną liczbę bajtów, które może reprezentować wolumin.|
|`unsigned long long free`|Reprezentuje liczbę bajtów, które nie są używane do reprezentowania danych w woluminie.|
|`unsigned long long available`|Reprezentuje liczbę bajtów, które są dostępne do reprezentowania danych w woluminie.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<filesystem>

**Przestrzeń nazw:** std:: eksperymentalne:: filesystem

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Nawigacja w systemie plików (C++)](../standard-library/file-system-navigation.md)
