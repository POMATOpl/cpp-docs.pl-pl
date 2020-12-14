---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4743'
title: Ostrzeżenie kompilatora (poziom 1) C4743
ms.date: 05/13/2019
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: a8c8bcd4ef0e4d7084da34e033be4194da11727f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228485"
---
# <a name="compiler-warning-level-1-c4743"></a>Ostrzeżenie kompilatora (poziom 1) C4743

*Typ "Type*" ma inny rozmiar w "*plik1*" i "*plik2*": *Liczba* i *Liczba* bajtów

Zmienna zewnętrzna przywoływana lub zdefiniowana w dwóch plikach ma różne typy w tych plikach, a kompilator ustalił, że rozmiar zmiennej w *plik1* różni się od rozmiaru zmiennej w *plik2*.

## <a name="remarks"></a>Uwagi

Istnieje ważna sytuacja, w której to ostrzeżenie może być emitowane dla języka C++. Jeśli deklarujesz te same typy o tej samej nazwie w dwóch różnych plikach, jeśli te deklaracje zawierają funkcje wirtualne, a deklaracje nie są takie same, kompilator może emitować C4744 ostrzeżeń dla tabel funkcji wirtualnych. Ostrzeżenie występuje, ponieważ istnieją dwie tabele funkcji wirtualnych o różnych rozmiarach dla tego samego typu, a konsolidator musi wybrać jedną z nich do uwzględnienia w pliku wykonywalnym.  Istnieje możliwość, że program może wywołać niewłaściwą funkcję wirtualną.

Aby rozwiązać to ostrzeżenie, należy użyć tej samej definicji typu lub użyć różnych nazw dla typów lub zmiennych.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4743. Aby go skompilować, Umieść oba pliki w tym samym folderze, a następnie uruchom polecenie  

```cmd
cl /EHsc /W1 /GL /O2 C4743a.cpp C4743b.cpp
```

```cpp
// C4743a.cpp
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
};

void C::f1(void) {}
void C::f2(void) {}
void C::f3(void) {}
C q;
```

```cpp
// C4743b.cpp
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
    virtual void f4(void);
    virtual void f5(void);
};

void C::f4(void) {}
void C::f5(void) {}
C x;

int main() {}
```
