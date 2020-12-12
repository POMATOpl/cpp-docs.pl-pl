---
description: 'Dowiedz się więcej o: definiowania bloków __asm jako makr C'
title: Definiowanie bloków __asm jako makr C
ms.date: 08/30/2018
helpviewer_keywords:
- macros, __asm blocks
- Visual C, macros
- __asm keyword [C++], as C macros
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
ms.openlocfilehash: a0fe13acdd5a75fd86fd8107396632a5c6e7c283
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117840"
---
# <a name="defining-__asm-blocks-as-c-macros"></a>Definiowanie bloków __asm jako makr C

**Specyficzne dla firmy Microsoft**

Makra języka C oferują wygodną metodę wstawiania kodu zestawu do kodu źródłowego, ale wymagają one dodatkowej opieki, ponieważ makro rozszerza się w jedną linię logiczną. Aby utworzyć makra bez problemów, wykonaj następujące reguły:

- Umieść **`__asm`** blok w nawiasach klamrowych.

- Umieść **`__asm`** słowo kluczowe przed każdą instrukcją zestawu.

- Używaj starych stylów języka C ( `/* comment */` ) zamiast komentarzy w stylu zestawu ( `; comment` ) lub jednowierszowych komentarzy w języku c ( `// comment` ).

W poniższym przykładzie zdefiniowano proste makro:

```cpp
#define PORTIO __asm      \
/* Port output */         \
{                         \
   __asm mov al, 2        \
   __asm mov dx, 0xD007   \
   __asm out dx, al       \
}
```

Na pierwszy rzut oka ostatnie trzy **`__asm`** słowa kluczowe pozornie są zbędne. Są one jednak zbędne, ponieważ makro rozszerza się w jeden wiersz:

```cpp
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }
```

Trzecie i czwarte **`__asm`** słowo kluczowe są zbędne jako separatory instrukcji. Jedyne separatory instrukcji rozpoznawane w **`__asm`** blokach są znakiem nowego wiersza i **`__asm`** słowem kluczowym. Ponieważ blok zdefiniowany jako makro jest jedną linią logiczną, należy oddzielić każdą instrukcję instrukcją **`__asm`** .

Nawiasy klamrowe są również niezbędne. Jeśli zostaną pominięte, kompilator może być pomylony przez instrukcje C lub C++ w tym samym wierszu z prawej strony wywołania makra. Bez zamykającego nawiasu klamrowego kompilator nie może stwierdzić, gdzie zatrzyma kod zestawu i widzi instrukcje C lub C++ po **`__asm`** bloku jako instrukcje zestawu.

Komentarze w stylu zestawu, które zaczynają się średnikiem (**;**), przejdź do końca wiersza. Powoduje to problemy z makrami, ponieważ kompilator ignoruje wszystko po komentarzu, aż do końca linii logicznej. Ta sama wartość dotyczy komentarzy jednowierszowych C lub C++ ( `// comment` ). Aby zapobiec błędom, należy użyć starych stylów języka C ( `/* comment */` ) w **`__asm`** blokach zdefiniowanych jako makra.

**`__asm`** Blok zapisany jako makro języka C może przyjmować argumenty. W przeciwieństwie do zwykłego makra C, **`__asm`** makro nie może zwracać wartości. Dlatego nie można używać takich makr w wyrażeniach C i C++.

Należy zachować ostrożność, aby nie wywoływać makr tego typu. Na przykład wywoływanie makra języka zestawu w funkcji zadeklarowanej z **`__fastcall`** Konwencją może spowodować nieoczekiwane wyniki. (Zobacz [Używanie i zachowywanie rejestrów w zestawie wbudowanym](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)).

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Asembler wbudowany](../../assembler/inline/inline-assembler.md)<br/>
