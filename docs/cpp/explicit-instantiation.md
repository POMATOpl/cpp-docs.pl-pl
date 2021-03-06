---
description: 'Dowiedz się więcej na temat: jawne Tworzenie wystąpienia'
title: Jawne tworzenie wystąpienia
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
ms.openlocfilehash: c3d6587490215627a867b7e20d49a50a089940da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273478"
---
# <a name="explicit-instantiation"></a>Jawne tworzenie wystąpienia

Można użyć jawnego tworzenia wystąpienia, aby utworzyć wystąpienie klasy lub funkcji z szablonem bez faktycznego używania jej w kodzie. Ponieważ jest to przydatne w przypadku tworzenia plików biblioteki (. lib), które używają szablonów do dystrybucji, definicje szablonu bez wystąpień nie są umieszczane w plikach obiektu (. obj).

Ten kod jawnie tworzy wystąpienia `MyStack` dla **`int`** zmiennych i sześciu elementów:

```cpp
template class MyStack<int, 6>;
```

Ta instrukcja tworzy Tworzenie wystąpienia `MyStack` bez rezerwowania żadnego magazynu dla obiektu. Kod jest generowany dla wszystkich elementów członkowskich.

Następny wiersz jawnie tworzy wystąpienie tylko funkcji członkowskiej konstruktora:

```cpp
template MyStack<int, 6>::MyStack( void );
```

Można jawnie utworzyć wystąpienia szablonów funkcji przy użyciu określonego argumentu typu, aby ponownie je zadeklarować, jak pokazano w przykładzie w [konkretyzacji szablonu funkcji](../cpp/function-template-instantiation.md).

Możesz użyć **`extern`** słowa kluczowego, aby zapobiec automatycznemu tworzeniu wystąpienia elementów członkowskich. Na przykład:

```cpp
extern template class MyStack<int, 6>;
```

Analogicznie, można oznaczyć określonych elementów członkowskich jako zewnętrzne i nie utworzyć wystąpienia:

```cpp
extern template MyStack<int, 6>::MyStack( void );
```

Możesz użyć **`extern`** słowa kluczowego, aby uniemożliwić kompilatorowi generowanie tego samego kodu wystąpienia w więcej niż jednym module obiektu. Należy utworzyć wystąpienie funkcji szablonu przy użyciu określonych parametrów szablonu jawnego w co najmniej jednym połączonym module, jeśli funkcja jest wywoływana, lub podczas kompilowania programu wystąpi błąd konsolidatora.

> [!NOTE]
> **`extern`** Słowo kluczowe w specjalizacji ma zastosowanie tylko do funkcji Członkowskich zdefiniowanych poza treścią klasy. Funkcje zdefiniowane wewnątrz deklaracji klasy są uznawane za wbudowane funkcje i zawsze są tworzone.

## <a name="see-also"></a>Zobacz też

[Szablony funkcji](../cpp/function-templates.md)
