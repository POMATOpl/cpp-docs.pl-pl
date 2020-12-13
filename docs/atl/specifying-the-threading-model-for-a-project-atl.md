---
description: Dowiedz się więcej o tym, jak określić model wątkowości dla projektu (ATL)
title: Określanie modelu wątkowości projektu (ALT)
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
ms.openlocfilehash: 81bf8413a2118797ec0e0c177a06468b8e3c7ba0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138479"
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Określanie modelu wątkowości projektu (ALT)

Następujące makra są dostępne do określenia modelu wątkowości projektu ATL:

|Makro|Wskazówki dotyczące korzystania z programu|
|-----------|--------------------------|
|_ATL_SINGLE_THREADED|Zdefiniuj, czy wszystkie obiekty korzystają z modelu pojedynczego wątku.|
|_ATL_APARTMENT_THREADED|Zdefiniuj, czy co najmniej jeden z obiektów ma używać wątków apartamentu.|
|_ATL_FREE_THREADED|Zdefiniuj, czy co najmniej jeden z obiektów ma korzystać z wątków bezpłatnych, czy neutralnych. Istniejący kod może zawierać odwołania do odpowiadającego mu makra [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded).|

Jeśli nie określisz żadnego z tych makr dla projektu, _ATL_FREE_THREADED będą obowiązywać.

Makra mają wpływ na wydajność w czasie wykonywania w następujący sposób:

- Określenie makra odnoszące się do obiektów w projekcie może poprawić wydajność w czasie wykonywania.

- Określanie wyższego poziomu makr, na przykład jeśli określisz _ATL_APARTMENT_THREADED, gdy wszystkie obiekty są jednowątkowe, znacznie obniży wydajność w czasie wykonywania.

- Określenie niższego poziomu makra, na przykład jeśli określisz _ATL_SINGLE_THREADED, gdy jeden lub więcej obiektów będzie używać wątków Apartment lub wolnych wątków, może spowodować niepowodzenie działania aplikacji w czasie wykonywania.

Zobacz [Opcje, Kreator prostych obiektów ATL,](../atl/reference/options-atl-simple-object-wizard.md) Aby uzyskać opis modeli wątkowości dostępnych dla obiektu ATL.

## <a name="see-also"></a>Zobacz też

[Pojęcia](../atl/active-template-library-atl-concepts.md)
