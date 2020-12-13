---
description: Dowiedz się więcej na temat klasy numpunct_byname
title: numpunct_byname — Klasa
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: e4e6352f9f65b2a726acf3f8f5f8ede9bffe54f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338035"
---
# <a name="numpunct_byname-class"></a>numpunct_byname — Klasa

Szablon klasy pochodnej opisuje obiekt, który może stanowić `numpunct` aspekt danego ustawienia regionalnego, co pozwala na formatowanie i interpunkcję wyrażeń liczbowych i logicznych.

## <a name="syntax"></a>Składnia

```cpp
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

};
```

## <a name="remarks"></a>Uwagi

Jego zachowanie zależy od [nazwanych](../standard-library/locale-class.md#name) ustawień regionalnych `_Locname` . Konstruktor inicjuje swój obiekt podstawowy z [numpunct](../standard-library/numpunct-class.md#numpunct) \<CharType> ( `_Refs` ).

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
