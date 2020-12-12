---
description: 'Dowiedz się więcej na temat: TypeName'
title: typename
ms.date: 11/04/2016
f1_keywords:
- typename_cpp
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
ms.openlocfilehash: 3bc1385412d23d947c75967c2dc79bee78bbcd28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145798"
---
# <a name="typename"></a>typename

W obszarze definicje szablonu program dostarcza wskazówkę do kompilatora, że nieznany identyfikator jest typem. Na listach parametrów szablonu służy do określania parametru typu.

## <a name="syntax"></a>Składnia

```
typename identifier;
```

## <a name="remarks"></a>Uwagi

Tego słowa kluczowego należy użyć, jeśli nazwa w definicji szablonu jest kwalifikowana nazwa, która jest zależna od argumentu szablonu; jest opcjonalne, jeśli kwalifikowana nazwa nie jest zależna. Aby uzyskać więcej informacji, zobacz [Szablony i rozpoznawanie nazw](../cpp/templates-and-name-resolution.md).

**`typename`** może być używany przez dowolny typ dowolnego miejsca w deklaracji lub definicji szablonu. Nie jest to dozwolone na liście klas bazowych, chyba że jako argument szablonu dla klasy podstawowej szablonu.

```cpp
template <class T>
class C1 : typename T::InnerType // Error - typename not allowed.
{};
template <class T>
class C2 : A<typename T::InnerType>  // typename OK.
{};
```

**`typename`** Słowo kluczowe może być również używane zamiast **`class`** na listach parametrów szablonu. Na przykład następujące instrukcje są semantycznie równoważne:

```cpp
template<class T1, class T2>...
template<typename T1, typename T2>...
```

## <a name="example"></a>Przykład

```cpp
// typename.cpp
template<class T> class X
{
   typename T::Y m_y;   // treat Y as a type
};

int main()
{
}
```

## <a name="see-also"></a>Zobacz także

[Szablony](../cpp/templates-cpp.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)
