---
description: Dowiedz się więcej na temat klasy ctype_byname
title: ctype_byname — Klasa
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: cc5f44e1c544d2088030621b684c9e070175d695
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233139"
---
# <a name="ctype_byname-class"></a>ctype_byname — Klasa

Szablon klasy pochodnej opisuje obiekt, który może być używany jako zestaw reguł CType dla danego ustawienia regionalnego, co umożliwia klasyfikację znaków i konwersję znaków między zestawami znaków w przypadku i natywnym i lokalnym.

## <a name="syntax"></a>Składnia

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>Uwagi

Jego zachowanie zależy od nazwanych ustawień regionalnych `_Locname` . Każdy Konstruktor inicjuje swój obiekt podstawowy z [CType](../standard-library/ctype-class.md) \<CharType> ( `_Refs` ) lub odpowiednikiem klasy bazowej `ctype<char>` .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
