---
description: 'Dowiedz się więcej na temat: zagadnienia dotyczące pisania kodu prologu/epilogu'
title: Zagadnienia dotyczące pisania kodu Prolog-Epilog
ms.date: 11/04/2016
helpviewer_keywords:
- layouts, stack frame
- stack frame layout
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: 3b8addec-e809-48e4-b1d0-5bad133bd4b8
ms.openlocfilehash: 65416e915afa95a27658e2c7517da8f2868dfef9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293290"
---
# <a name="considerations-when-writing-prologepilog-code"></a>Zagadnienia dotyczące pisania kodu prologu/epilogu

**Specyficzne dla firmy Microsoft**

Przed zapisaniem własnych sekwencji kodu prologu i epilogu ważne jest, aby zrozumieć, jak Ramka stosu jest rozłożone. Warto również wiedzieć, jak używać wstępnie zdefiniowanej stałej **__LOCAL_SIZE** .

## <a name="cstack-frame-layout"></a><a name="_clang_c_stack_frame_layout"></a> Układ ramki CStack

W tym przykładzie pokazano standardowy kod prologu, który może pojawić się w 32-bitowej funkcji:

```
push     ebp                 ; Save ebp
mov      ebp, esp            ; Set stack frame pointer
sub      esp, localbytes     ; Allocate space for locals
push     <registers>         ; Save registers
```

Zmienna `localbytes` reprezentuje liczbę bajtów potrzebnych na stosie dla zmiennych lokalnych a zmienna `registers` jest symbolem zastępczym reprezentującym listę rejestrów, które mają być zapisane na stosie. Po umieszczeniu rejestrów na stosie, można tam umieścić wszelkie inne dane. Poniżej przedstawiono odpowiadający kod epilogu:

```
pop      <registers>         ; Restore registers
mov      esp, ebp            ; Restore stack pointer
pop      ebp                 ; Restore ebp
ret                          ; Return from function
```

Stos zawsze powiększa się w dół (od najwyższego do najniższego adresu pamięci). Podstawowy wskaźnik (`ebp`) wskazuje na umieszczoną wartość `ebp`. Obszar zmiennych lokalnych rozpoczyna się od `ebp-2`. Aby uzyskać dostęp do zmiennych lokalnych, należy obliczyć przesunięcie z `ebp` przez odjęcie odpowiedniej wartości od `ebp`.

## <a name="the-__local_size-constant"></a><a name="_clang_the___local_size_constant"></a> __LOCAL_SIZE stała

Kompilator dostarcza stałą, **__LOCAL_SIZE**, do użycia w bloku asemblera wbudowanego kodu prologu funkcji. Stała jest używana do alokowania miejsca dla zmiennych lokalnych na ramce stosu w niestandardowym kodzie prologu.

Kompilator określa wartość **__LOCAL_SIZE**. Wartość to całkowita liczba bajtów wszystkich zmiennych lokalnych zdefiniowanych przez użytkownika i zmiennych tymczasowych wygenerowanych przez kompilator. **__LOCAL_SIZE** można używać tylko jako bezpośredniego operandu; nie można jej użyć w wyrażeniu. Nie wolno zmieniać lub ponownie definiować wartości tej stałej. Na przykład:

```
mov      eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov      eax, [ebp - __LOCAL_SIZE]   ;Error
```

Poniższy przykład funkcji owies, która zawiera niestandardowe sekwencje prologu i epilogu używa **__LOCAL_SIZE** w sekwencji prologu:

```
__declspec ( naked ) func()
{
   int i;
   int j;

   __asm      /* prolog */
      {
      push   ebp
      mov      ebp, esp
      sub      esp, __LOCAL_SIZE
      }

   /* Function body */

   __asm      /* epilog */
      {
      mov      esp, ebp
      pop      ebp
      ret
      }
}
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcje bez nadruku](../c-language/naked-functions.md)
