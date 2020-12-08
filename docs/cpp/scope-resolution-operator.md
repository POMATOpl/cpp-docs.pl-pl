---
title: 'Operator rozpoznawania zakresu: `::`'
description: Dowiedz się, w jaki sposób operator rozpoznawania zakresu `::` działa w standardowym języku C++.
ms.date: 12/06/2020
f1_keywords:
- '::'
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.openlocfilehash: ff774d9fcca9f68cb2925af82c55ef438ab4d71a
ms.sourcegitcommit: 7b131db4ed39bddb4a456ebea402f47c5cbd69d3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/07/2020
ms.locfileid: "96776534"
---
# <a name="scope-resolution-operator-"></a>Operator rozpoznawania zakresu: `::`

Operator rozpoznawania zakresu służy **`::`** do identyfikowania i niejednoznaczności identyfikatorów używanych w różnych zakresach. Aby uzyskać więcej informacji na temat zakresu, zobacz [SCOPE](../cpp/scope-visual-cpp.md).

## <a name="syntax"></a>Składnia

> *`qualified-id`*:\
> &emsp;*`nested-name-specifier`***`template`** <sub>wybór</sub>*`unqualified-id`*

> *`nested-name-specifier`*:\
> &emsp;**`::`**\
> &emsp;*`type-name`* **`::`**\
> &emsp;*`namespace-name`* **`::`**\
> &emsp;*`decltype-specifier`* **`::`**\
> &emsp;*`nested-name-specifier`* *`identifier`* **`::`**\
> &emsp;*`nested-name-specifier`***`template`** <sub>opt</sub> wybór *`simple-template-id`***`::`**

> *`unqualified-id`*:\
> &emsp;*`identifier`*\
> &emsp;*`operator-function-id`*\
> &emsp;*`conversion-function-id`*\
> &emsp;*`literal-operator-id`*\
> &emsp;**`~`** *`type-name`*\
> &emsp;**`~`** *`decltype-specifier`*\
> &emsp;*`template-id`*

## <a name="remarks"></a>Uwagi

`identifier`Może to być zmienna, funkcja lub wartość wyliczenia.

## <a name="use--for-classes-and-namespaces"></a>Użyj `::` dla klas i przestrzeni nazw

Poniższy przykład pokazuje, jak operator rozpoznawania zakresu jest używany z przestrzeniami nazw i klasami:

```cpp
namespace NamespaceA{
    int x;
    class ClassA {
    public:
        int x;
    };
}

int main() {

    // A namespace name used to disambiguate
    NamespaceA::x = 1;

    // A class name used to disambiguate
    NamespaceA::ClassA a1;
    a1.x = 2;
}
```

Operator rozpoznawania zakresu bez kwalifikatora zakresu odwołuje się do globalnej przestrzeni nazw.

```cpp
namespace NamespaceA{
    int x;
}

int x;

int main() {
    int x;

    // the x in main()
    x = 0;
    // The x in the global namespace
    ::x = 1;

    // The x in the A namespace
    NamespaceA::x = 2;
}
```

Możesz użyć operatora rozpoznawania zakresu, aby zidentyfikować element członkowski **`namespace`** lub zidentyfikować przestrzeń nazw, która wyznacza przestrzeń nazw składowej w **`using`** dyrektywie. W poniższym przykładzie można użyć `NamespaceC` do kwalifikowania `ClassB` , nawet jeśli `ClassB` została zadeklarowana w przestrzeni nazw `NamespaceB` , ponieważ `NamespaceB` została wyznaczony `NamespaceC` przez **`using`** dyrektywę.

```cpp
namespace NamespaceB {
    class ClassB {
    public:
        int x;
    };
}

namespace NamespaceC{
    using namespace NamespaceB;
}

int main() {
    NamespaceB::ClassB b_b;
    NamespaceC::ClassB c_b;

    b_b.x = 3;
    c_b.x = 4;
}
```

Można używać łańcuchów operatorów rozpoznawania zakresu. W poniższym przykładzie `NamespaceD::NamespaceD1` identyfikuje zagnieżdżoną przestrzeń nazw `NamespaceD1` i `NamespaceE::ClassE::ClassE1` identyfikuje klasę zagnieżdżoną `ClassE1` .

```cpp
namespace NamespaceD{
    namespace NamespaceD1{
        int x;
    }
}

namespace NamespaceE{
    class ClassE{
    public:
        class ClassE1{
        public:
            int x;
        };
    };
}

int main() {
    NamespaceD:: NamespaceD1::x = 6;
    NamespaceE::ClassE::ClassE1 e1;
    e1.x = 7  ;
}
```

## <a name="use--for-static-members"></a>Użyj `::` dla statycznych składowych

Aby wywołać statyczne elementy członkowskie klas, należy użyć operatora rozpoznawania zakresu.

```cpp
class ClassG {
public:
    static int get_x() { return x;}
    static int x;
};

int ClassG::x = 6;

int main() {

    int gx1 = ClassG::x;
    int gx2 = ClassG::get_x();
}
```

## <a name="use--for-scoped-enumerations"></a>Użyj `::` dla wyliczeń z zakresem

Operator rozpoznania zakresu jest również używany z wartościami [deklaracji wyliczenia](../cpp/enumerations-cpp.md)wyliczeniowego w zakresie, jak w poniższym przykładzie:

```cpp
enum class EnumA{
    First,
    Second,
    Third
};

int main() {
    EnumA enum_value = EnumA::First;
}
```

## <a name="see-also"></a>Zobacz także

[Wbudowane operatory, pierwszeństwo i łączność języka C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Namespaces](../cpp/namespaces-cpp.md)
