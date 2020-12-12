---
description: 'Dowiedz się więcej o: specyfikatory Storage-Class z deklaracjami funkcji'
title: Specyfikatory klasy magazynowania z deklaracjami funkcji
ms.date: 11/04/2016
helpviewer_keywords:
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
ms.openlocfilehash: acf3bc1928715878281b4603bf842f248976265f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296774"
---
# <a name="storage-class-specifiers-with-function-declarations"></a>Specyfikatory klasy magazynowania z deklaracjami funkcji

Można użyć **`static`** lub **`extern`** specyfikator klasy magazynu w deklaracjach funkcji. Funkcje zawsze mają globalne okresy istnienia.

**Specyficzne dla firmy Microsoft**

Deklaracje funkcji na poziomie wewnętrznym mają takie samo znaczenie jak deklaracje funkcji na poziomie zewnętrznym. Oznacza to, że funkcja jest widoczna z punktu deklaracji w pozostałej części jednostki translacji, nawet jeśli jest zadeklarowana w zakresie lokalnym.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

Reguły widoczności dla funkcji różnią się nieco od reguł dla zmiennych w następujący sposób:

- Funkcja zadeklarowana jako **`static`** jest widoczna tylko w pliku źródłowym, w którym jest zdefiniowana. Funkcje w tym samym pliku źródłowym mogą wywołać **`static`** funkcję, ale funkcje w innych plikach źródłowych nie mogą uzyskać do nich dostępu bezpośrednio według nazwy. Można zadeklarować inną **`static`** funkcję o tej samej nazwie w innym pliku źródłowym bez konfliktu.

- Funkcje zadeklarowane jako **`extern`** są widoczne w całym pliku źródłowym w programie (chyba że później ponownie zadeklarujesz taką funkcję jako **`static`** ). Każda funkcja może wywołać **`extern`** funkcję.

- Deklaracje funkcji, które pomijają specyfikator klasy magazynowania, są **`extern`** domyślnie.

**Specyficzne dla firmy Microsoft**

Firma Microsoft umożliwia ponowne definiowanie **`extern`** identyfikatora jako **`static`** .

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasy magazynu w języku C](../c-language/c-storage-classes.md)
