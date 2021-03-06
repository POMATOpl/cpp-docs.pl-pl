---
description: 'Dowiedz się więcej na temat: zakres i widoczność'
title: Zakres i widoczność
ms.date: 11/04/2016
helpviewer_keywords:
- scope, levels
- visibility
- file scope [C++]
ms.assetid: a019eb7c-66ed-46a7-bc9f-89a963930a56
ms.openlocfilehash: 188fbedad87e370e8b5b1e7dabc475e301ca3f4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292834"
---
# <a name="scope-and-visibility"></a>Zakres i widoczność

„Widoczność” identyfikatora określa części programu, w których można się do niego odwoływać (jego „zakres”). Identyfikator jest widoczny (tzn. może zostać użyty) tylko w częściach programu wchodzących w skład jego „zakresu”, który może być ograniczony (w celu zwiększenia restrykcyjności) do pliku, funkcji, bloku lub prototypu funkcji, w którym występuje. Zakres identyfikatora jest częścią programu, w której może być używana nazwa. Jest to czasami nazywane „zakresem słownikowym”. Istnieją cztery rodzaje zakresów: funkcji, pliku, bloku i prototypu funkcji.

Wszystkie identyfikatory z wyjątkiem etykiet mają zakres uzależniony od poziomu, na którym występuje deklaracja. Dla każdego rodzaju zakresu, widocznością identyfikatorów w programie rządzą następujące zasady:

Zakres pliku Deklarator lub specyfikator typu dla identyfikatora z zakresem pliku pojawia się poza dowolnym blokiem lub listą parametrów i jest dostępny z dowolnego miejsca w jednostce tłumaczenia po jego deklaracji. Nazwy identyfikatorów z zakresem pliku są często nazywane „global” lub „external”. Zakres globalnego identyfikatora rozpoczyna się w miejscu jego definicji lub deklaracji i kończy się na końcu jednostki translacji.

Zakres funkcji etykieta jest jedynym rodzajem identyfikatora, który ma zakres funkcji. Etykieta jest niejawnie zadeklarowana przez jej użycie w instrukcji. Nazwy etykiet muszą być unikatowe w obrębie danej funkcji. (Aby uzyskać więcej informacji na temat etykiet i nazw etykiet, zobacz [instrukcje goto i labeled](../c-language/goto-and-labeled-statements-c.md).).

Zakres bloku Deklarator lub specyfikator typu dla identyfikatora z zakresem bloku pojawia się wewnątrz bloku lub wewnątrz listy deklaracji parametrów formalnych w definicji funkcji. Jest widoczny tylko od punktu jego deklaracji lub definicji do końca bloku, zawierającego jego deklarację lub definicję. Jej zakres jest ograniczony do tego bloku i wszelkich bloków zagnieżdżonych w tym bloku i kończy się nawiasem klamrowym, który zamyka skojarzony blok. Takie identyfikatory są czasami nazywane „zmiennymi lokalnymi”.

Zakres prototypu funkcji Deklarator lub specyfikator typu dla identyfikatora z zakresem prototypu funkcji pojawia się na liście deklaracji parametrów w prototypie funkcji (nie jest częścią deklaracji funkcji). Jej zakres kończy się z końcem deklaratora funkcji.

Odpowiednie deklaracje dotyczące tworzenia zmiennych widocznych w innych plikach źródłowych są opisane w [klasach magazynu](../c-language/c-storage-classes.md). Jednak zmienne i funkcje zadeklarowane na poziomie zewnętrznym ze **`static`** specyfikatorem klasy magazynu są widoczne tylko w pliku źródłowym, w którym są zdefiniowane. Wszystkie pozostałe funkcje są widoczne globalnie.

## <a name="see-also"></a>Zobacz też

[Okres istnienia, zakres, widoczność i połączenie](../c-language/lifetime-scope-visibility-and-linkage.md)
