---
description: 'Dowiedz się więcej na temat: pliki Wizard-Generated dostawcy'
title: Pliki dostawcy generowane przez kreatora
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: 95c9641f10acef4a55b8de15752eb125e75d874a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316898"
---
# <a name="provider-wizard-generated-files"></a>Pliki dostawcy generowane przez kreatora

::: moniker range="msvc-160"

Kreator dostawcy OLE DB ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

::: moniker-end

::: moniker range="<=msvc-150"

**Kreator dostawcy OLE DB ATL** generuje następujące pliki. W poniższych tematach użyto krótkiej nazwy *niestandardowej*, ale dokładne nazwy plików zależą od wyboru dokonanego podczas tworzenia dostawcy.

|Nazwa pliku|Opis|
|---------------|-----------------|
|*Niestandardowe* RS. cpp|Zawiera metodę pomocnika poleceń `Execute` i mapę kolumn dostawcy.|
|*Niestandardowe* DS. h|Implementuje obiekt źródła danych. Ten plik nagłówkowy zawiera mapę właściwości dla właściwości źródła danych.|
|*Niestandardowe* RS. h|Implementuje obiekty Command i Rowset. Ten plik nagłówkowy zawiera mapę właściwości dla zestawu wierszy i właściwości polecenia.|
|*Niestandardowe* Sess. h|Implementuje obiekt session. Ten plik nagłówkowy zawiera mapę właściwości dla właściwości sesji.|
|*Custom*. RGS|Zawiera zarejestrowane obiekty wygenerowane przez **Kreatora dostawcy OLE DB**.|

::: moniker-end

## <a name="see-also"></a>Zobacz też

[Tworzenie dostawcy OLE DB](../../data/oledb/creating-an-ole-db-provider.md)<br/>
