---
description: 'Dowiedz się więcej o: &lt; wyjątki &gt; Typedefs'
title: '&lt;&gt;definicje typów wyjątków'
ms.date: 11/04/2016
f1_keywords:
- exception/std::exception_ptr
- exception/std::terminate_handler
- exception/std::unexpected_handler
ms.assetid: 2a338480-35e2-46f7-b223-52d4e84a5768
ms.openlocfilehash: 5df3f49a66cced171d96c2dedad7b239535519a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324532"
---
# <a name="ltexceptiongt-typedefs"></a>&lt;&gt;definicje typów wyjątków

## <a name="exception_ptr"></a><a name="exception_ptr"></a> exception_ptr

Typ, który opisuje wskaźnik do wyjątku.

```cpp
typedef unspecified exception_ptr;
```

### <a name="remarks"></a>Uwagi

Nieokreślona Klasa wewnętrzna, która jest używana do implementowania `exception_ptr` typu.

Użyj `exception_ptr` obiektu, aby odwołać się do bieżącego wyjątku lub wystąpienia wyjątku określonego przez użytkownika. W implementacji firmy Microsoft wyjątek jest reprezentowany przez strukturę [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) . Każdy `exception_ptr` obiekt zawiera pole odwołania wyjątku, które wskazuje kopię `EXCEPTION_RECORD` struktury, która reprezentuje wyjątek.

Podczas deklarowania `exception_ptr` zmiennej zmienna nie jest skojarzona z żadnym wyjątkiem. To znaczy, że pole odwołania wyjątku ma wartość NULL. Taki `exception_ptr` obiekt jest nazywany exception_ptr o *wartości null*.

Użyj `current_exception` funkcji or, `make_exception_ptr` Aby przypisać wyjątek do `exception_ptr` obiektu. Po przypisaniu wyjątku do `exception_ptr` zmiennej pole odwołania wyjątku zmiennej wskazuje kopię wyjątku. Jeśli nie ma wystarczającej ilości pamięci do skopiowania wyjątku, pole odwołania wyjątku wskazuje kopię wyjątku [std:: bad_alloc](../standard-library/bad-alloc-class.md) . Jeśli `current_exception` Funkcja or `make_exception_ptr` nie może skopiować wyjątku z jakiegokolwiek innego powodu, funkcja wywołuje `terminate` funkcję CRT, aby wyjść z bieżącego procesu.

Pomimo nazwy, `exception_ptr` obiekt nie jest samo wskaźnikiem. Nie przestrzega on semantyki wskaźnika i nie można go używać z operatorami dostępu do elementów członkowskich wskaźnika ( `->` ) ani pośrednich (*). `exception_ptr`Obiekt nie ma publicznych składowych danych ani funkcji Członkowskich.

**Porównanie**

`==` `!=` Do porównywania dwóch obiektów można użyć operatorów równości () i nierówności () `exception_ptr` . Operatory nie porównują wartości binarnej (wzorca bitowego) `EXCEPTION_RECORD` struktur, które reprezentują wyjątki. Zamiast tego operatory porównują adresy w polu odwołanie wyjątku `exception_ptr` obiektów. W związku z tym `exception_ptr` wartość null i wartości null są porównywane jako równe.

## <a name="terminate_handler"></a><a name="terminate_handler"></a> terminate_handler

Typ opisuje wskaźnik do funkcji odpowiedniej do użycia jako `terminate_handler` .

```cpp
typedef void (*terminate_handler)();
```

### <a name="remarks"></a>Uwagi

Typ opisuje wskaźnik do funkcji odpowiedni do użytku jako program obsługi zakończenia.

### <a name="example"></a>Przykład

Zobacz [set_terminate](../standard-library/exception-functions.md#set_terminate) , aby zapoznać się z przykładem użycia `terminate_handler` .

## <a name="unexpected_handler"></a><a name="unexpected_handler"></a> unexpected_handler

Typ opisuje wskaźnik do funkcji odpowiedniej do użycia jako `unexpected_handler` .

```cpp
typedef void (*unexpected_handler)();
```

### <a name="example"></a>Przykład

Zobacz [set_unexpected](../standard-library/exception-functions.md#set_unexpected) , aby zapoznać się z przykładem użycia `unexpected_handler` .
