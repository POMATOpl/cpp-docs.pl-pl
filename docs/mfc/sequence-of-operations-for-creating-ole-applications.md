---
description: 'Dowiedz się więcej o: Sekwencja operacji tworzenia aplikacji OLE'
title: Sekwencja operacji przy tworzeniu aplikacji OLE
ms.date: 11/04/2016
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
ms.openlocfilehash: 2bce49d569c6d3def536cbe9386cafbe08ccdbfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217565"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>Sekwencja operacji przy tworzeniu aplikacji OLE

W poniższej tabeli przedstawiono rolę i rolę struktury w temacie Tworzenie łączy OLE i osadzanie aplikacji. Reprezentują one opcje, a nie sekwencje kroków do wykonania.

### <a name="creating-ole-applications"></a>Tworzenie aplikacji OLE

|Zadanie|Masz|Struktura wykonuje|
|----------|------------|------------------------|
|Utwórz składnik COM.|Uruchom Kreatora aplikacji MFC. Wybierz pozycję **Full-Server** lub **mini-Server** na karcie **Obsługa dokumentu złożonego** .|Struktura generuje aplikację szkieletową z włączoną funkcją składnika COM. Wszystkie możliwości COM można przenieść do istniejącej aplikacji z zastosowaniem tylko niewielkiej modyfikacji.|
|Tworzenie aplikacji kontenera od podstaw.|Uruchom Kreatora aplikacji MFC. Wybierz pozycję **kontener** na karcie **Obsługa dokumentu złożonego** . przy użyciu widok klasy przejdź do edytora kodu źródłowego. Wypełnij kod dla funkcji obsługi modelu COM.|Struktura generuje aplikację szkieletową, która umożliwia wstawianie obiektów COM utworzonych przez aplikacje składnika COM (serwer).|
|Utwórz aplikację, która obsługuje automatyzację od podstaw.|Uruchom Kreatora aplikacji MFC. Wybierz **automatyzację** z karty **funkcje zaawansowane** . Użyj widok klasy, aby udostępnić metody i właściwości w aplikacji w celu automatyzacji.|Struktura generuje aplikację szkieletową, która może być aktywowana i zautomatyzowana przez inne aplikacje.|

## <a name="see-also"></a>Zobacz też

[Kompilowanie na platformie](../mfc/building-on-the-framework.md)<br/>
[Sekwencja operacji do kompilowania aplikacji MFC](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[Sekwencja operacji do tworzenia kontrolek ActiveX](../mfc/sequence-of-operations-for-creating-activex-controls.md)<br/>
[Sekwencja operacji związanych z tworzeniem aplikacji bazy danych](../mfc/sequence-of-operations-for-creating-database-applications.md)
