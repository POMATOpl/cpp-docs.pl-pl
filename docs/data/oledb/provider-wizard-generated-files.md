---
title: Pliki dostawcy generowane przez kreatora
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 3bc680e5999c077dda384823ec4f67d2456af284
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924321"
---
# <a name="provider-wizard-generated-files"></a>Pliki dostawcy generowane przez kreatora

::: moniker range="msvc-160"

Kreator dostawcy OLE DB ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

::: moniker-end

::: moniker range="<=msvc-150"

**Kreator dostawcy OLE DB ATL** generuje następujące pliki. W poniższych tematach użyto krótkiej nazwy *niestandardowej* , ale dokładne nazwy plików zależą od wyboru dokonanego podczas tworzenia dostawcy.

|Nazwa pliku|Opis|
|---------------|-----------------|
|*Niestandardowe* RS. cpp|Zawiera metodę pomocnika poleceń `Execute` i mapę kolumn dostawcy.|
|*Niestandardowe* DS. h|Implementuje obiekt źródła danych. Ten plik nagłówkowy zawiera mapę właściwości dla właściwości źródła danych.|
|*Niestandardowe* RS. h|Implementuje obiekty Command i Rowset. Ten plik nagłówkowy zawiera mapę właściwości dla zestawu wierszy i właściwości polecenia.|
|*Niestandardowe* Sess. h|Implementuje obiekt session. Ten plik nagłówkowy zawiera mapę właściwości dla właściwości sesji.|
|*Custom* . RGS|Zawiera zarejestrowane obiekty wygenerowane przez **Kreatora dostawcy OLE DB** .|

::: moniker-end

## <a name="see-also"></a>Zobacz także

[Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
