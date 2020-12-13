---
description: 'Dowiedz się więcej o: przykładowa Klasa kontenera'
title: Sample Container — Klasa
ms.date: 11/04/2016
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
ms.openlocfilehash: 728cec44462a8e09aad7f87000520f0fa5a15b3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148879"
---
# <a name="sample-container-class"></a>Sample Container — Klasa

> [!NOTE]
> Ten temat znajduje się w dokumentacji języka Microsoft C++ jako niefunkcjonalny przykład kontenerów używanych w standardowej bibliotece języka C++. Aby uzyskać więcej informacji, zobacz [kontenery standardowej biblioteki języka C++](../standard-library/stl-containers.md).

Opisuje obiekt, który kontroluje różnej długości sekwencji elementów, zazwyczaj typu `Ty` . Sekwencja jest przechowywana na różne sposoby, w zależności od rzeczywistego kontenera.

Konstruktor kontenera lub funkcja członkowska może odwoływać się do konstruktora **ty**(**const Ty&**) lub funkcji **ty:: operator =**(**const br&**). Jeśli takie wywołanie zgłasza wyjątek, obiekt kontenera jest zobowiązany do utrzymania jego integralności i ponownego zgłoszenia wszelkich wyjątków, które wychwytuje. Można bezpiecznie zamienić, przypisać do, wymazać lub zniszczyć obiekt kontenera po wystąpieniu jednego z tych wyjątków. Ogólnie rzecz biorąc, nie można w inny sposób przewidzieć stanu sekwencji kontrolowanej przez obiekt kontenera.

Niektóre dodatkowe zastrzeżenia:

- Jeśli wyrażenie `~Ty` zgłasza wyjątek, stan wynikający z obiektu kontenera jest niezdefiniowany.

- Jeśli kontener przechowuje obiekt alokatora *Al*, a *Al* zgłasza wyjątek inny niż w wyniku wywołania `al.allocate` , wynikowy stan obiektu kontenera jest niezdefiniowany.

- Jeśli kontener przechowuje *zgodność* obiektu funkcji, aby określić sposób uporządkowania kontrolowanej sekwencji, a funkcja *COMP* zgłasza wyjątek dowolnego rodzaju, stan wyniku obiektu kontenera jest niezdefiniowany.

Klasy kontenerów zdefiniowane przez standardową bibliotekę języka C++ spełniają kilka dodatkowych wymagań, zgodnie z opisem w poniższych akapitach.

[Lista](../standard-library/list-class.md) szablonów klas kontenerów zawiera deterministyczne i przydatne zachowanie, nawet w obecności wyjątków opisanych powyżej. Na przykład, jeśli wyjątek jest zgłaszany podczas wstawiania jednego lub kilku elementów, kontener pozostaje niezmienione i zostanie ponownie zgłoszony wyjątek.

Dla *wszystkich* klas kontenerów zdefiniowanych przez standardową bibliotekę języka C++, jeśli wyjątek jest zgłaszany podczas wywołań do następujących funkcji składowych, `insert` , `push_back` , lub `push_front` , kontener pozostaje niezmienione i wyjątek jest ponownie zgłaszany.

Dla *wszystkich* klas kontenerów zdefiniowanych przez standardową bibliotekę języka C++ żaden wyjątek nie jest zgłaszany podczas wywołań do następujących funkcji Członkowskich: `pop_back` , `pop_front` .

Funkcja członkowska [Wymaż](../standard-library/container-class-erase.md) zgłasza wyjątek tylko wtedy, gdy operacja kopiowania (konstrukcja przypisania lub kopiowania) zgłosi wyjątek.

Ponadto żaden wyjątek nie jest zgłaszany podczas kopiowania iteratora zwróconego przez funkcję członkowską.

Funkcja [wymiany](../standard-library/container-class-swap.md) funkcji składowej sprawia, że dodatkowe niesie obietnice zwiększenia dla *wszystkich* klas kontenerów zdefiniowanych przez standardową bibliotekę języka C++:

- Funkcja członkowska zgłasza wyjątek tylko wtedy, gdy kontener przechowuje obiekt alokatora Al i `al` zgłasza wyjątek podczas kopiowania.

- Odwołania, wskaźniki i Iteratory, które wyznaczają elementy z wymienianych sekwencji są prawidłowe.

Obiekt klasy kontenera zdefiniowanej przez standardową bibliotekę języka C++ przydziela i zwalnia magazyn dla sekwencji, która kontroluje przez przechowywany obiekt typu `Alloc` , który jest zazwyczaj parametrem szablonu. Taki obiekt alokatora musi mieć ten sam interfejs zewnętrzny, co obiekt klasy `allocator<Ty>` . W szczególności `Alloc` musi być tego samego typu co `Alloc::rebind<value_type>::other`

Dla *wszystkich* klas kontenerów zdefiniowanych przez standardową bibliotekę języka C++ funkcja członkowska `Alloc get_allocator const;` zwraca kopię przechowywanego obiektu alokatora. Należy zauważyć, że przechowywany obiekt alokatora *nie* jest kopiowany po przypisaniu obiektu kontenera. Wszystkie konstruktory inicjują wartość przechowywaną w `allocator` , do, `Alloc` Jeśli Konstruktor nie zawiera parametru alokatora.

Zgodnie ze standardem C++ Klasa kontenera zdefiniowana przez standardową bibliotekę języka C++ może przyjąć, że:

- Wszystkie obiekty klasy są `Alloc` porównywane.

- Typ `Alloc::const_pointer` jest taki sam jak `const Ty *` .

- Typ `Alloc::const_reference` jest taki sam jak `const Ty&` .

- Typ `Alloc::pointer` jest taki sam jak `Ty *` .

- Typ `Alloc::reference` jest taki sam jak `Ty&` .

W tej implementacji jednak kontenery nie upraszczają założeń. W ten sposób działają poprawnie z obiektami alokatora, które są bardziej ambitne podejście:

- Wszystkie obiekty klasy nie `Alloc` muszą porównywać wartości równej. (Można zachować wiele pul magazynu).

- Typ nie `Alloc::const_pointer` musi być taki sam jak `const Ty *` . (Stała wskaźnik może być klasą).

- Typ nie `Alloc::pointer` musi być taki sam jak `Ty *` . (Wskaźnik może być klasą).

## <a name="requirements"></a>Wymagania

**Nagłówek**: \<sample container>

## <a name="see-also"></a>Zobacz też

[\<sample container>](../standard-library/sample-container.md)
