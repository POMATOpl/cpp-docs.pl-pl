---
description: 'Dowiedz się więcej o: Tworzenie dostawcy OLE DB'
title: Tworzenie dostawcy OLE DB
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
ms.openlocfilehash: 69dc9311a79f2739636633b2d268343a92d2dac9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287804"
---
# <a name="creating-an-ole-db-provider"></a>Tworzenie dostawcy OLE DB

Zalecanym sposobem utworzenia dostawcy OLE DB jest użycie kreatorów do utworzenia projektu ATL COM i dostawcy, a następnie zmodyfikowanie plików przy użyciu szablonów OLE DB. Podczas dostosowywania dostawcy można skomentować niepożądane właściwości i dodać opcjonalne interfejsy.

Podstawowe kroki są następujące:

1. Użyj **Kreatora projektu ATL** do utworzenia podstawowych plików projektu i **Kreatora dostawcy ATL OLEDB** , aby utworzyć dostawcę (wybierz **dostawcę ATL OLEDB** z **zainstalowanego**  >  **Visual C++**  >  **ATL** folderu w obszarze **Dodaj nowy element**).

   > [!NOTE]
   > Projekt musi zawierać obsługę MFC przed dodaniem **dostawcy ATL OLEDB**.

1. Zmodyfikuj kod w `Execute` metodzie w [CCustomRowset (Customs. h)](cmyproviderrowset-myproviderrs-h.md). Aby zapoznać się z przykładem, zobacz [odczytywanie ciągów do dostawcy OLE DB](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

1. Edytuj mapy właściwości w [CustomDS. h](cmyprovidersource-myproviderds-h.md), [CustomSess. h](cmyprovidersession-myprovidersess-h.md)i [niestandardowych. h](cmyproviderrowset-myproviderrs-h.md). Kreator tworzy mapy właściwości, które zawierają wszystkie właściwości, które może zaimplementować dostawca. Zapoznaj się z właściwościami mapy i Usuń lub Skomentuj właściwości, które nie muszą być obsługiwane przez dostawcę.

1. Zaktualizuj PROVIDER_COLUMN_MAP, które można znaleźć w [CCustomRowset (Customs. h)](cmyproviderrowset-myproviderrs-h.md). Aby zapoznać się z przykładem, zobacz artykuł [Przechowywanie ciągów w dostawcy OLE DB](../../data/oledb/storing-strings-in-the-ole-db-provider.md).

1. Gdy jesteś gotowy do testowania dostawcy, możesz go przetestować, próbując znaleźć dostawcę w wyliczeniu dostawcy. Aby zapoznać się z przykładami kodu testowego, który znajduje się w wyliczeniu, zobacz przykłady [catdb](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb) i [dbview](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) lub przykład [wdrażania prostego konsumenta](../../data/oledb/implementing-a-simple-consumer.md).

1. Dodaj wszelkie dodatkowe interfejsy. Aby zapoznać się z przykładem, zobacz [ulepszanie prostego dostawcy Read-Only](../../data/oledb/enhancing-the-simple-read-only-provider.md).

   > [!NOTE]
   > Domyślnie kreatorzy generują kod, który jest zgodny OLE DB poziomu 0. Aby upewnić się, że aplikacja pozostaje zgodna poziom 0, nie usuwaj żadnych interfejsów generowanych przez kreatora z kodu.

## <a name="see-also"></a>Zobacz też

[Przykład CatDB: przeglądarka schematu źródła danych](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb)<br/>
[Przykład DBVIEWER: przeglądarka bazy danych](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)
