---
description: 'Dowiedz się więcej na temat: Conditional-Expression — operator'
title: Operator wyrażenia warunkowego
ms.date: 11/04/2016
helpviewer_keywords:
- conditional operators
- operators [C++], conditional
- expressions [C++], conditional
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
ms.openlocfilehash: 4b11b0f3ed132459f4e1608922e111c3b5bf2a98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293316"
---
# <a name="conditional-expression-operator"></a>Operator wyrażenia warunkowego

C ma jeden operator Trzyelementowy: operator wyrażenia warunkowego (**?:**).

## <a name="syntax"></a>Składnia

*wyrażenie warunkowe*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie logiczne OR*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie logiczne or*  **?**  *wyrażenie*  **:**  *wyrażenie warunkowe*

*Wyrażenie logiczne or* musi mieć typ całkowity, zmiennoprzecinkowy lub wskaźnik. Jest on oceniany pod względem równoważności do 0. Punkt sekwencji jest następujący: *logiczny-lub-Expression*. Obliczanie operandów odbywa się w następujący sposób:

- Jeśli *logiczne-lub-Expression* nie jest równe 0, *wyrażenie* jest oceniane. Wynik obliczania wyrażenia jest określony przez *wyrażenie* niebędące terminalem. (Oznacza to, że *wyrażenie* jest oceniane tylko wtedy *, gdy wyrażenie logiczne or* ma wartość true).

- Jeśli *wyrażenie logiczne or* jest równe 0, obliczane jest *wyrażenie warunkowe* . Wynikiem wyrażenia jest wartość *wyrażenia warunkowego*. (Oznacza to, że *wyrażenie warunkowe* jest oceniane tylko wtedy *, gdy logiczne-lub-Expression* ma wartość false.)

Należy zauważyć, że obliczane jest *wyrażenie* lub *wyrażenie warunkowe* , ale nie oba jednocześnie.

Typ wyniku operacji warunkowej zależy od typu *wyrażenia* lub operand *warunkowego wyrażenia* w następujący sposób:

- Jeśli *wyrażenie* lub *wyrażenie warunkowe* ma typ całkowity lub zmiennoprzecinkowy (ich typy mogą być różne), operator wykonuje typowe konwersje arytmetyczne. Typ wyniku jest typem operandów po konwersji.

- Jeśli wyrażenie *i* *wyrażenie warunkowe* mają tę samą strukturę, Unię lub typ wskaźnika, typ wyniku jest taka sama jak struktura, Unia lub typ wskaźnika.

- Jeśli oba operandy mają typ **`void`** , wynik ma typ **`void`** .

- Jeśli którykolwiek z operandów jest wskaźnikiem do obiektu dowolnego typu, a drugi operand jest wskaźnikiem do **`void`** , wskaźnik do obiektu jest konwertowany na wskaźnik do, **`void`** a wynik jest wskaźnikiem do **`void`** .

- Jeśli wyrażenie *lub* *wyrażenie warunkowe* jest wskaźnikiem, a drugi operand jest wyrażeniem stałym o wartości 0, typ wyniku jest typem wskaźnika.

W porównaniu typu dla wskaźników, wszelkie Kwalifikatory typu ( **`const`** lub **`volatile`** ) w typie, do którego punkty wskaźnika są nieznaczące, ale typ wyniku dziedziczy kwalifikatory z obu składników warunku.

## <a name="examples"></a>Przykłady

W poniższych przykładach pokazano użycie operatora warunkowego:

```
j = ( i < 0 ) ? ( -i ) : ( i );
```

Ten przykład przypisuje wartość bezwzględną `i` do `j` . Jeśli `i` jest mniejszy niż 0, `-i` jest przypisany do `j` . Jeśli `i` jest większy lub równy 0, `i` jest przypisany do `j` .

```cpp
void f1( void );
void f2( void );
int x;
int y;
    .
    .
    .
( x == y ) ? ( f1() ) : ( f2() );
```

W tym przykładzie `f1` są zadeklarowane dwie funkcje, i `f2` , dwie zmienne `x` i `y` . W dalszej części programu, jeśli dwie zmienne mają tę samą wartość, funkcja `f1` jest wywoływana. W przeciwnym razie `f2` jest wywoływana.

## <a name="see-also"></a>Zobacz też

[Operator warunkowy: ? :](../cpp/conditional-operator-q.md)
