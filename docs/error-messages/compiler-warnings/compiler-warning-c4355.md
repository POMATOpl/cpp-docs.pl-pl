---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4355'
title: Ostrzeżenie kompilatora C4355
ms.date: 11/04/2016
f1_keywords:
- C4355
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
ms.openlocfilehash: fd4d38aae7a3728370c89cb2298438dbc0ba616c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180776"
---
# <a name="compiler-warning-c4355"></a>Ostrzeżenie kompilatora C4355

'this': używany na liście inicjatora bazowego elementu członkowskiego

**`this`** Wskaźnik jest prawidłowy tylko wewnątrz niestatycznych funkcji składowych. Nie można jej użyć na liście inicjatorów dla klasy bazowej.

Konstruktory klasy podstawowej i konstruktory elementów członkowskich klasy są wywoływane przed **`this`** konstruktorem. W efekcie przeszedł wskaźnik do niekonstruowanego obiektu do innego konstruktora. Jeśli te inne konstruktory uzyskują dostęp do dowolnych elementów członkowskich lub wywołują funkcje składowe, wynik będzie niezdefiniowany. Nie należy używać wskaźnika, **`this`** dopóki cała konstrukcja nie zostanie ukończona.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Poniższy przykład generuje C4355:

```cpp
// C4355.cpp
// compile with: /w14355 /c
#include <tchar.h>

class CDerived;
class CBase {
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function() = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase {
public:
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor
   virtual void function() {};
};

CBase::~CBase() {
   m_pDerived -> function();
}

int main() {
   CDerived myDerived;
}
```
