---
description: 'Dowiedz się więcej na temat: specyfikator końcowy'
title: final, specyfikator
ms.date: 11/04/2016
f1_keywords:
- final_CPP
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
ms.openlocfilehash: 5fd6ee3c23a455c4316593cc089c26c34477709d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242616"
---
# <a name="final-specifier"></a>final, specyfikator

Możesz użyć słowa kluczowego **Final** , aby wyznaczyć funkcje wirtualne, których nie można zastąpić w klasie pochodnej. Można go również użyć do wyznaczania klas, które nie mogą być dziedziczone.

## <a name="syntax"></a>Składnia

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>Uwagi

**wersja ostateczna** jest zależna od kontekstu i ma specjalne znaczenie tylko wtedy, gdy jest używana po deklaracji funkcji lub nazwie klasy; w przeciwnym razie nie jest zarezerwowanym słowem kluczowym.

Gdy **końcowa** jest używana w deklaracjach klas, `base-classes` jest opcjonalną częścią deklaracji.

## <a name="example"></a>Przykład

Poniższy przykład używa **końcowego** słowa kluczowego, aby określić, że nie można zastąpić funkcji wirtualnej.

```cpp
class BaseClass
{
    virtual void func() final;
};

class DerivedClass: public BaseClass
{
    virtual void func(); // compiler error: attempting to
                         // override a final function
};
```

Aby dowiedzieć się, jak określić, że funkcje składowe mogą zostać zastąpione, zobacz [specyfikator override](../cpp/override-specifier.md).

W następnym przykładzie używane jest słowo kluczowe **Final** , aby określić, że Klasa nie może być dziedziczona.

```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // compiler error: BaseClass is
                                     // marked as non-inheritable
{
};
```

## <a name="see-also"></a>Zobacz też

[Słowa kluczowe](../cpp/keywords-cpp.md)<br/>
[Specyfikator przesłonięcia](../cpp/override-specifier.md)
