---
description: 'Dowiedz się więcej o: mapowania właściwości'
title: Mapy właściwości
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 30b277451d871de45902661f7b7e56cbc7409c97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316911"
---
# <a name="property-maps"></a>Mapy właściwości

Przy użyciu sesji, zestawu wierszy i opcjonalnego obiektu polecenia każdy dostawca obsługuje jedną lub więcej właściwości. Te właściwości są zdefiniowane w mapach właściwości przechowywanych w plikach nagłówkowych utworzonych przez **Kreatora dostawcy OLE DB**. Każdy plik nagłówkowy zawiera mapę właściwości w OLE DB grupy właściwości zdefiniowane dla obiektu lub obiektów zdefiniowanych w tym pliku. Plik nagłówkowy, który zawiera obiekt źródła danych, zawiera również mapę właściwości [Właściwości DataSource](/previous-versions/windows/desktop/ms724188(v=vs.85)). `Session.h` zawiera mapę właściwości dla [właściwości sesji](/previous-versions/windows/desktop/ms714221(v=vs.85)). Zestaw wierszy i obiekty poleceń znajdują się w jednym pliku nagłówkowym o nazwie *ProjectName* RS. h. Te właściwości są elementami członkowskimi grupy [Właściwości zestawu wierszy](/previous-versions/windows/desktop/ms711252(v=vs.85)) .

## <a name="see-also"></a>Zobacz też

[Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
