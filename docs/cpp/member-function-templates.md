---
title: Szablony funkcji członkowskich
ms.date: 11/04/2016
helpviewer_keywords:
- function templates, member functions
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
ms.openlocfilehash: 8514c8ffe630f5bc44d8d287d6ccf08c7755e3a0
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008563"
---
# <a name="member-function-templates"></a>Szablony funkcji członkowskich

Termin szablon elementu członkowskiego odwołuje się zarówno do szablonów funkcji składowych, jak i szablonów klas zagnieżdżonych. Szablony funkcji Członkowskich są funkcjami szablonu, które są elementami członkowskimi szablonu klasy lub klasy.

Funkcje składowe mogą być szablonami funkcji w kilku kontekstach. Wszystkie funkcje szablonów klas są ogólne, ale nie są określane jako szablony elementów członkowskich lub szablony funkcji składowych. Jeśli te funkcje elementu członkowskiego korzystają z własnych argumentów szablonu, są one uznawane za szablony funkcji składowych.

## <a name="example-declare-member-function-templates"></a>Przykład: Zadeklaruj szablony funkcji składowych

Szablony funkcji członkowskich klas nienależących do szablonu lub szablonu są deklarowane jako szablony funkcji ze swoimi parametrami szablonu.

```cpp
// member_function_templates.cpp
struct X
{
   template <class T> void mf(T* t) {}
};

int main()
{
   int i;
   X* x = new X();
   x->mf(&i);
}
```

## <a name="example-member-function-template-of-template-class"></a>Przykład: element członkowski szablonu klasy szablonu

Poniższy przykład pokazuje szablon funkcji składowej klasy szablonu.

```cpp
// member_function_templates2.cpp
template<typename T>
class X
{
public:
   template<typename U>
   void mf(const U &u)
   {
   }
};

int main()
{
}
```

## <a name="example-define-member-templates-outside-class"></a>Przykład: Definiowanie szablonów elementów członkowskich poza klasą

```cpp
// defining_member_templates_outside_class.cpp
template<typename T>
class X
{
public:
   template<typename U>
   void mf(const U &u);
};

template<typename T> template <typename U>
void X<T>::mf(const U &u)
{
}

int main()
{
}
```

## <a name="example-templated-user-defined-conversion"></a>Przykład: konwersja zdefiniowana przez użytkownika

Lokalne klasy nie mogą mieć szablonów składowych.

Funkcje szablonu elementu członkowskiego nie mogą być funkcjami wirtualnymi i nie mogą przesłonić funkcji wirtualnych z klasy podstawowej, gdy są one zadeklarowane przy użyciu takiej samej nazwy jak funkcja wirtualna klasy bazowej.

W poniższym przykładzie przedstawiono zdefiniowaną przez użytkownika konwersję:

```cpp
// templated_user_defined_conversions.cpp
template <class T>
struct S
{
   template <class U> operator S<U>()
   {
      return S<U>();
   }
};

int main()
{
   S<int> s1;
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.
}
```

## <a name="see-also"></a>Zobacz też

[Szablony funkcji](../cpp/function-templates.md)
