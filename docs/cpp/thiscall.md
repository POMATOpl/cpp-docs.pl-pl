---
title: __thiscall
description: Dowiedz się więcej na temat konwencji wywoływania __thiscall specyficznych dla firmy Microsoft dla funkcji członkowskich klasy x86 w programie Microsoft C++.
ms.date: 05/22/2020
f1_keywords:
- __thiscall
- __thiscall_cpp
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
ms.openlocfilehash: 9b11dcf8dee928b687f942639ed72ead3659614b
ms.sourcegitcommit: 25f6d52eb9e5d84bd0218c46372db85572af81da
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94448454"
---
# `__thiscall`

Konwencja wywoływania **specyficzna dla firmy Microsoft** **`__thiscall`** jest używana w funkcjach składowych klasy języka C++ w architekturze x86. Jest to domyślna konwencja wywoływania używana przez funkcje członkowskie, które nie używają argumentów zmiennych ( `vararg` Functions).

W obszarze **`__thiscall`** , wywoływany czyści stos, co jest niemożliwe dla `vararg` funkcji. Argumenty są wypychane na stosie od prawej do lewej. **`this`** Wskaźnik jest przesyłany za pośrednictwem rejestracji ECX, a nie na stosie.

Na komputerach ARM, ARM64 i x64 **`__thiscall`** jest akceptowane i ignorowane przez kompilator. Wynika to z tego, że domyślnie używają konwencji wywoływania opartej na rejestrze.

Jedną z przyczyn użycia **`__thiscall`** jest Klasa, której funkcje członkowskie **`__clrcall`** domyślnie używają. W takim przypadku można użyć, **`__thiscall`** Aby udostępnić poszczególne funkcje członkowskie z kodu natywnego.

Podczas kompilowania przy użyciu [`/clr:pure`](../build/reference/clr-common-language-runtime-compilation.md) , wszystkie funkcje i wskaźniki funkcji są, **`__clrcall`** chyba że określono inaczej. **`/clr:pure`** **`/clr:safe`** Opcje kompilatora i są przestarzałe w programie visual Studio 2015 i nie są obsługiwane w programie visual Studio 2017.

`vararg` funkcje członkowskie używają **`__cdecl`** konwencji wywoływania. Wszystkie argumenty funkcji są wypychane na stosie z **`this`** wskaźnikiem umieszczonym na stosie.

Ponieważ ta konwencja wywoływania ma zastosowanie tylko do języka C++, nie ma schematu dekoracji nazwy C.

Podczas definiowania niestatycznej funkcji składowej klasy, określ modyfikator konwencji wywoływania tylko w deklaracji. Nie musisz określać go ponownie w definicji poza wierszem. Kompilator używa konwencji wywoływania określonej podczas deklaracji w punkcie definicji.

## <a name="see-also"></a>Zobacz też

[Przekazywanie argumentów i konwencje nazewnictwa](../cpp/argument-passing-and-naming-conventions.md)
