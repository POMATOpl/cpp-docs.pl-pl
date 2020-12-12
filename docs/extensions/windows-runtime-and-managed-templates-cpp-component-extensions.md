---
description: 'Dowiedz się więcej na temat: środowisko wykonawcze systemu Windows i szablony zarządzane (C++/CLI i C++/CX)'
title: Środowisko wykonawcze systemu Windows i zarządzane szablony (C++/CLI i C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
ms.openlocfilehash: 75b39c58bc42c23da313525f125dc98abdb0866b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274037"
---
# <a name="windows-runtime-and-managed-templates-ccli-and-ccx"></a>Środowisko wykonawcze systemu Windows i zarządzane szablony (C++/CLI i C++/CX)

Szablony umożliwiają zdefiniowanie prototypu środowisko wykonawcze systemu Windows lub typu środowiska uruchomieniowego języka wspólnego, a następnie wystąpienie wariacji tego typu przy użyciu różnych parametrów typu szablonu.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

Możesz tworzyć szablony z typów wartości lub odwołań.  Aby uzyskać więcej informacji na temat tworzenia typów wartości lub odwołań, zobacz [klasy i struktury](classes-and-structs-cpp-component-extensions.md).

Aby uzyskać więcej informacji na temat szablonów klas standardowego języka C++, zobacz [Szablony klas](../cpp/class-templates.md).

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

(Nie ma żadnych uwag dla tej funkcji języka, które mają zastosowanie tylko do środowisko wykonawcze systemu Windows).

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/ZW`

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

Istnieją pewne ograniczenia dotyczące tworzenia szablonów klas z typów zarządzanych, które przedstawiono w poniższych przykładach kodu.

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`

### <a name="examples"></a>Przykłady

Istnieje możliwość utworzenia wystąpienia typu ogólnego z parametrem szablonu typu zarządzanego, ale nie można utworzyć wystąpienia szablonu zarządzanego z parametrem szablonu typu ogólnego. Wynika to z faktu, że typy ogólne są rozwiązane w czasie wykonywania. Aby uzyskać więcej informacji, zobacz [typy ogólne i szablony (C++/CLI)](generics-and-templates-visual-cpp.md).

```cpp
// managed_templates.cpp
// compile with: /clr /c

generic<class T>
ref class R;

template<class T>
ref class Z {
   // Instantiate a generic with a template parameter.
   R<T>^ r;    // OK
};

generic<class T>
ref class R {
   // Cannot instantiate a template with a generic parameter.
   Z<T>^ z;   // C3231
};
```

Typ ogólny lub funkcja nie może być zagnieżdżona w zarządzanym szablonie.

```cpp
// managed_templates_2.cpp
// compile with: /clr /c

template<class T> public ref class R {
   generic<class T> ref class W {};   // C2959
};
```

Nie można uzyskać dostępu do szablonów zdefiniowanych w przywoływanym zestawie przy użyciu składni języka C++/CLI, ale można użyć odbicia. Jeśli szablon nie jest skonkretyzowany, nie jest emitowany w metadanych. Jeśli zostanie utworzone wystąpienie szablonu, w metadanych będą wyświetlane tylko funkcje członkowskie, do których się odwoływano.

```cpp
// managed_templates_3.cpp
// compile with: /clr

// Will not appear in metadata.
template<class T> public ref class A {};

// Will appear in metadata as a specialized type.
template<class T> public ref class R {
public:
   // Test is referenced, will appear in metadata
   void Test() {}

   // Test2 is not referenced, will not appear in metadata
   void Test2() {}
};

// Will appear in metadata.
generic<class T> public ref class G { };

public ref class S { };

int main() {
   R<int>^ r = gcnew R<int>;
   r->Test();
}
```

Można zmienić zarządzany modyfikator klasy w częściowej specjalizacji lub jawnej specjalizacji szablonu klasy.

```cpp
// managed_templates_4.cpp
// compile with: /clr /c

// class template
// ref class
template <class T>
ref class A {};

// partial template specialization
// value type
template <class T>
value class A <T *> {};

// partial template specialization
// interface
template <class T>
interface class A<T%> {};

// explicit template specialization
// native class
template <>
class A <int> {};
```

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platform .NET i platformy UWP](component-extensions-for-runtime-platforms.md)
