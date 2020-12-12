---
description: 'Dowiedz się więcej na temat: bezpieczeństwo wątków w standardowej bibliotece języka C++'
title: Bezpieczeństwo wątku w standardowej bibliotece C++
ms.date: 11/04/2016
helpviewer_keywords:
- thread safety
- C++ Standard Library, thread safety
- thread safety, C++ Standard Library
ms.assetid: 9351c8fb-4539-4728-b0e9-226e2ac4284b
ms.openlocfilehash: ff5d8960b2fc8a79acbfb4fc1d0be508865714e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289637"
---
# <a name="thread-safety-in-the-c-standard-library"></a>Bezpieczeństwo wątku w standardowej bibliotece C++

Poniższe reguły zabezpieczeń wątku dotyczą wszystkich klas w standardowej bibliotece języka C++ — obejmuje to `shared_ptr` , jak opisano poniżej.  Są czasami dostępne silniejsze gwarancje — na przykład standardowe obiekty iostream, zgodnie z poniższym opisem, i typy przeznaczone dla wielowątkowości, takie jak w [\<atomic>](../standard-library/atomic.md) .

Obiekt jest bezpieczny wątkowo do odczytu z wielu wątków. Na przykład, mając obiekt A, można bezpiecznie odczytać z wątku 1 i z wątku 2 jednocześnie.

Jeśli obiekt jest zapisywany do jednego wątku, wszystkie operacje odczytu i zapisu do tego obiektu w tym samym lub innych wątkach muszą być chronione. Na przykład, mając obiekt A, jeśli wątek 1 jest zapisywany w, wówczas wątek 2 musi być zablokowany do odczytu lub zapisu w.

Można bezpiecznie odczytywać i zapisywać dane w jednym wystąpieniu typu, nawet jeśli inny wątek odczytuje lub zapisuje w innym wystąpieniu tego samego typu. Na przykład obiekty A i B tego samego typu są bezpieczne, gdy jest zapisywany w wątku 1 i B jest odczytywany w wątku 2.

## <a name="shared_ptr"></a>shared_ptr

Wiele wątków może jednocześnie odczytywać i zapisywać różne [shared_ptr](../standard-library/shared-ptr-class.md) obiektów, nawet gdy obiekty są kopiowane, które współdzielą własność.

## <a name="iostream"></a>iostream

W przypadku standardowych obiektów iostream,,,,, `cin` `cout` `cerr` `clog` `wcin` `wcout` `wcerr` i `wclog` postępuj zgodnie z tymi samymi regułami co inne klasy, z wyjątkiem tego wyjątku: można bezpiecznie pisać do obiektu z wielu wątków. Na przykład wątek 1 może zapisywać do [cout](../standard-library/iostream.md#cout) w tym samym czasie co wątek 2. Jednak może to spowodować, że dane wyjściowe z dwóch wątków mają być mieszane.

> [!NOTE]
> Odczyt z buforu strumienia nie jest uważany za operację odczytu. Zamiast tego uznaje się, że jest to operacja zapisu, ponieważ stan klasy jest zmieniany.

## <a name="see-also"></a>Zobacz też

[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)
