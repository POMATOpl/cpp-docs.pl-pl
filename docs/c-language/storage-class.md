---
description: Dowiedz się więcej o klasie Storage
title: Klasa magazynu
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
ms.openlocfilehash: 87f53c38b2f71acc15499a496e98b1f9c7173210
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296735"
---
# <a name="storage-class"></a>Klasa magazynu

Specyfikator klasy magazynowania w definicji funkcji zawiera funkcję **`extern`** lub **`static`** klasę magazynu.

## <a name="syntax"></a>Składnia

*definicja funkcji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deklaracja-specyfikators*<sub>opt</sub> *Attribute-SEQ*<sub>opt</sub> *deklarator* *deklaracji-list*<sub>opt</sub> *złożone-instrukcja*

/\**atrybut-seq* jest specyficzny dla firmy Microsoft\*/

*specyfikatory deklaracji*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Deklaracja* *specyfikatora klasy magazynu* —<sub>wybór</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;Deklaracja *specyfikatora typu* *— wybór specyfikatorów*<sub></sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;Deklaracja *kwalifikatora typu* *— wybór specyfikatorów*<sub></sub>

*specyfikator klasy magazynu*:/ \* dla definicji funkcji \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`extern`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`static`**

Jeśli definicja funkcji nie zawiera *specyfikatora klasy magazynu*, wartość domyślna klasy magazynu to **`extern`** . Można jawnie zadeklarować funkcję jako **`extern`** , ale nie jest to wymagane.

Jeśli deklaracja funkcji zawiera *specyfikator klasy magazynu* **`extern`** , identyfikator ma takie samo powiązanie jak wszelka widoczna deklaracja identyfikatora z zakresem pliku. Jeśli nie ma żadnej widocznej deklaracji z zakresem pliku, identyfikator ma powiązania zewnętrzne. Jeśli identyfikator ma zakres pliku i brak *specyfikatora klasy magazynu*, identyfikator ma powiązania zewnętrzne. Powiązania zewnętrzne oznaczają, że każde wystąpienie identyfikatora oznacza ten sam obiekt lub funkcję. Aby uzyskać więcej informacji na temat powiązania i zakresu plików, zobacz [okres istnienia, zakres, widoczność i połączenie](../c-language/lifetime-scope-visibility-and-linkage.md) .

Deklaracje funkcji zakresu bloku ze specyfikatorem klasy magazynu innym niż **`extern`** Generuj błędy.

Funkcja z **`static`** klasą magazynu jest widoczna tylko w pliku źródłowym, w którym jest zdefiniowana. Wszystkie inne funkcje, niezależnie od tego, czy są one **`extern`** klasą magazynu jawnie lub niejawnie, są widoczne w całym pliku źródłowym w programie. Jeśli **`static`** wymagana jest Klasa magazynu, musi być zadeklarowana w pierwszym wystąpieniu deklaracji (jeśli istnieje) funkcji i w definicji funkcji.

**Specyficzne dla firmy Microsoft**

Po włączeniu rozszerzeń Microsoft Funkcja zadeklarowana pierwotnie bez klasy magazynu (lub **`extern`** klasy magazynu) jest podaną **`static`** klasą magazynu, jeśli definicja funkcji znajduje się w tym samym pliku źródłowym, a definicja jawnie określa **`static`** klasę magazynu.

Podczas kompilowania z opcją kompilatora/ze, funkcje zadeklarowane w bloku przy użyciu **`extern`** słowa kluczowego mają globalną widoczność. Nie ma to zastosowania podczas kompilowania z opcją /Za. Na tej funkcji nie można polegać, jeżeli trzeba uwzględnić przenośność kodu źródłowego.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Definicje funkcji języka C](../c-language/c-function-definitions.md)
