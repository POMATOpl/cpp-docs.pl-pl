---
description: 'Dowiedz się więcej o: błąd kompilatora C3848'
title: Błąd kompilatora C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 8bd81f59927dd1b34c23148dd1e9bd69ec715609
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255382"
---
# <a name="compiler-error-c3848"></a>Błąd kompilatora C3848

wyrażenie typu "Type" spowoduje utratę niektórych kwalifikatorów const-volatile w celu wywołania funkcji "Function"

Zmienna z określonym nietrwałym typem const może wywołać tylko funkcje członkowskie zdefiniowane z tymi samymi lub większymi nietrwałymi atrybutami const.

Następujące przykłady generują C3848:

```cpp
// C3848.cpp
void glbFunc1()
{
}

typedef void (* pFunc1)();

struct S3
{
   operator pFunc1() // const
   {
      return &glbFunc1;
   }
};

int main()
{
   const S3 s3;
   s3();   // C3848, uncomment const qualifier
}
```
