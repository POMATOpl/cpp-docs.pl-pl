---
title: numpunct_byname — Klasa
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: da9259df8c527e44a4adea3a53be31b3c3ffc10b
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687607"
---
# <a name="numpunct_byname-class"></a>numpunct_byname — Klasa

Szablon klasy pochodnej opisuje obiekt, który może być `numpunct` aspektem danego ustawienia regionalnego, umożliwiając formatowanie i interpunkcję wyrażeń liczbowych i logicznych.

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

Jego zachowanie zależy od [nazwanych](../standard-library/locale-class.md#name) ustawień regionalnych `_Locname`. Konstruktor inicjuje swój obiekt podstawowy z [numpunct](../standard-library/numpunct-class.md#numpunct) \<CharType > (`_Refs`).

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<locale >

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz także

[Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
