---
description: Dowiedz się więcej na temat klasy time_put_byname
title: time_put_byname — Klasa
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: b519b28b7af8f5b54f9150d1d84f68cd6695bc49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167256"
---
# <a name="time_put_byname-class"></a>time_put_byname — Klasa

Szablon klasy pochodnej opisuje obiekt, który może być używany jako zestaw reguł ustawień regionalnych typu `time_put` \< CharType, OutputIterator > .

## <a name="syntax"></a>Składnia

```cpp
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```

### <a name="parameters"></a>Parametry

*_Locname*\
Nazwa ustawień regionalnych.

*_Refs*\
Początkowa liczba odwołań.

## <a name="remarks"></a>Uwagi

Jego zachowanie zależy od nazwanych [o nazwie](../standard-library/locale-class.md#name) ustawień regionalnych *_Locname*. Każdy Konstruktor inicjuje swój obiekt podstawowy z [time_put](../standard-library/time-put-class.md#time_put) \<CharType, OutputIterator> ( `_Refs` ).

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
