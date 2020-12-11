---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4398'
title: Ostrzeżenie kompilatora (poziom 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: ea88f81e44fe0520cd096e1904c49a306863496a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160431"
---
# <a name="compiler-warning-level-3-c4398"></a>Ostrzeżenie kompilatora (poziom 3) C4398

> "*zmienna*": globalny obiekt dla procesu może nie funkcjonować poprawnie z wieloma domenami aplikacji; Rozważ użycie __declspec (AppDomain)

## <a name="remarks"></a>Uwagi

Funkcja wirtualna z [__clrcall](../../cpp/clrcall.md) konwencją wywoływania w typie natywnym powoduje utworzenie tabeli dla każdej domeny aplikacji. Taka zmienna może nie poprawić prawidłowo, gdy jest używana w wielu domenach aplikacji.

Możesz rozwiązać to ostrzeżenie poprzez jawne oznaczenie zmiennej `__declspec(appdomain)` . W wersjach programu Visual Studio przed Visual Studio 2017 można rozwiązać to ostrzeżenie przez skompilowanie z **/CLR: Pure**, co powoduje domyślne zmienne globalne na domenę aplikacji. **/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

Aby uzyskać więcej informacji, [Zobacz](../../cpp/appdomain.md) [domeny aplikacji i aplikacje oraz Visual C++](../../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4398.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```
