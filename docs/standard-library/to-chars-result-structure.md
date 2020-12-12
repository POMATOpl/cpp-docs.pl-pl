---
description: Dowiedz się więcej na temat struktury to_chars_result
title: to_chars_result, struktura
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars_result
helpviewer_keywords:
- to_chars_result class
- to_chars_result structure
ms.openlocfilehash: fb043ba928f086549aea326419ec3a2d673723ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167191"
---
# <a name="to_chars_result-struct"></a>to_chars_result, struktura

## <a name="syntax"></a>Składnia

```cpp
struct to_chars_result {
    char* ptr;
    errc ec;
};
```

## <a name="members"></a>Elementy członkowskie

|Członek|Opis|
|--|--|
|`ptr`| Jeśli `ec` jest równa `errc{}` , konwersja zakończyła się pomyślnie i `ptr` jest wskaźnikiem jednostronnym-końcowym znaków pisanych. W przeciwnym razie `ptr` ma wartość `to_chars()` parametru `last` i zawartość zakresu \[ pierwszy, ostatni) nie są określone.|
|`ec` | Kod błędu konwersji. Aby uzyskać informacje o określonych kodach błędów, zobacz [`errc`](system-error-enums.md#errc) .|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<charconv>

**Przestrzeń nazw:** std

**Opcja kompilatora:** /std: c++ 17 lub nowsza, jest wymagana

## <a name="see-also"></a>Zobacz też

[to_chars](charconv-functions.md#to_chars)
