---
description: 'Dowiedz się więcej na temat: nothrow (C++)'
title: nothrow (C++)
ms.date: 01/03/2018
f1_keywords:
- nothrow_cpp
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
ms.openlocfilehash: 7e438541221fe097aefb2e52d190e223fa1cf2fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146253"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Specyficzne dla firmy Microsoft**

**`__declspec`** Rozszerzony atrybut, który może być używany w deklaracji funkcji.

## <a name="syntax"></a>Składnia

> *Typ zwracany* __declspec (nothrow) [*call-Convention*] *nazwa funkcji* ([*Lista argumentów*])

## <a name="remarks"></a>Uwagi

Zalecamy, aby cały nowy kod używał operatora [noexcept](noexcept-cpp.md) zamiast `__declspec(nothrow)` .

Ten atrybut informuje kompilator, że funkcja zadeklarowana i funkcje, które wywołuje, nigdy nie zgłasza wyjątku. Jednak nie wymusza zastosowania dyrektywy. Innymi słowy, nigdy nie powoduje wywołania [std:: terminate](../standard-library/exception-functions.md#terminate) , w przeciwieństwie do **`noexcept`** lub w trybie **std: C++ 17** (Visual Studio 2017 w wersji 15,5 i nowszej) `throw()` .

W modelu obsługi wyjątków synchronicznych, teraz, kompilator może wyeliminować Mechanics, aby śledzić okres istnienia niektórych niezawijanych obiektów w tej funkcji, i znacząco zmniejszyć rozmiar kodu. Zgodnie z poniższą dyrektywą preprocesora, trzy deklaracje funkcji są równoważne w trybie **/std: c++ 14** :

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

W **/std: tryb c++ 17** `throw()` nie jest odpowiednikiem innych, które są używane, `__declspec(nothrow)` ponieważ powoduje `std::terminate` wywoływanie, jeśli wyjątek jest zgłaszany przez funkcję.

`void __stdcall f3() throw();`Deklaracja używa składni zdefiniowanej przez Standard języka C++. W języku C++ 17 `throw()` słowo kluczowe było przestarzałe.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[__declspec](../cpp/declspec.md)<br/>
[noexcept](noexcept-cpp.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)
