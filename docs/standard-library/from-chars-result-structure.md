---
description: Dowiedz się więcej na temat struktury from_chars_result
title: from_chars_result, struktura
ms.date: 7/23/2020
f1_keywords:
- std::from_chars_result
helpviewer_keywords:
- from_chars_result class
- from_chars_result structure
ms.openlocfilehash: 894a687a4395e22538b384675af5b4ce57731f78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232281"
---
# <a name="from_chars_result-struct"></a>from_chars_result, struktura

## <a name="syntax"></a>Składnia

```cpp
struct from_chars_result {
    const char* ptr;
    errc ec;
};
```

|Członek|Opis|
|--|--|
|`ptr`| Jeśli `ec` jest równa `errc{}` , konwersja powiodła się i `ptr` wskazuje na pierwszy znak, który nie jest częścią rozpoznanego numeru. |
|`ec` | Kod błędu konwersji. Aby uzyskać informacje o określonych kodach błędów, zobacz [`errc`](system-error-enums.md#errc) .|

### <a name="remarks"></a>Uwagi

Przykład: Analiza `"1729cats"` jako dziesiętna liczba całkowita powiedzie się, a następnie `ptr` wskazuje, `'c'` że jest to pierwsza niebędąca cyfrą i jest również jedną z nich `"1729"` .

Jeśli żadne znaki nie są zgodne ze wzorcem numeru, `from_chars_result.ptr` wskazuje na `first` , i `from_chars_result.ec` is `errc::invalid_argument` .

Jeśli tylko niektóre znaki pasują do wzorca liczb, `from_chars_result.ptr` wskazuje pierwszy znak, który nie pasuje do wzorca lub ma wartość `last` parametru, jeśli wszystkie znaki są zgodne.

Jeśli przeanalizowana wartość nie będzie pasować do zakresu dla typu wykonywanej konwersji, `from_chars_result.ec` to `errc::result_out_of_range` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<charconv>

**Przestrzeń nazw:** std

**Opcja kompilatora:** /std: c++ 17 lub nowsza, jest wymagana

## <a name="see-also"></a>Zobacz też

[from_chars](charconv-functions.md#from_chars)
