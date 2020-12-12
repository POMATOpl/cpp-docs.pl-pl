---
description: Dowiedz się więcej na temat klasy moneypunct_byname
title: moneypunct_byname — Klasa
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct_byname
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
ms.openlocfilehash: b20293ac6788156f25f95878a5ab0098c178edec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277469"
---
# <a name="moneypunct_byname-class"></a>moneypunct_byname — Klasa

Szablon klasy pochodnej, który opisuje obiekt, który może być używany jako zestaw `moneypunct` reguł dla danego ustawienia regionalnego, co umożliwia formatowanie pola wejściowego pieniężnego lub pola walutowych danych wyjściowych.

## <a name="syntax"></a>Składnia

```cpp
template <class CharType, bool Intl = false>
class moneypunct_byname : public moneypunct<CharType, Intl>
{
public:
    explicit moneypunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit moneypunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~moneypunct_byname();

};
```

## <a name="remarks"></a>Uwagi

Jego zachowanie zależy od nazwanych ustawień regionalnych `_Locname` . Każdy Konstruktor inicjuje swój obiekt podstawowy z [moneypunct](../standard-library/moneypunct-class.md#moneypunct) \<CharType, Intl> ( `_Refs` ).

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
