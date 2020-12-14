---
description: Dowiedz się więcej na temat OLE-Related klas
title: Klasy związane z mechanizmem OLE
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: c54ebbedabc2e44095d06b0e842f7c73d5dbb43e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244033"
---
# <a name="ole-related-classes"></a>Klasy związane z mechanizmem OLE

Klasy te udostępniają wiele różnych usług, w tym od wyjątków do plików wejściowych i wyjściowych.

[COleObjectFactory](reference/coleobjectfactory-class.md)<br/>
Służy do tworzenia elementów na żądanie z innych kontenerów. Ta klasa służy jako klasa bazowa dla bardziej specyficznych typów fabryk, w tym `COleTemplateServer` .

[COleMessageFilter](reference/colemessagefilter-class.md)<br/>
Służy do zarządzania współbieżnością przy użyciu prostych wywołań procedur zdalnych OLE (LRPC).

[COleStreamFile](reference/colestreamfile-class.md)<br/>
Używa interfejsu COM, `IStream` Aby zapewnić `CFile` dostęp do plików złożonych. Ta klasa (pochodna od `CFile` ) umożliwia serializacji MFC Używanie magazynu strukturalnego OLE.

[CRectTracker](reference/crecttracker-class.md)<br/>
Służy do zezwalania na przeniesienie, zmianę rozmiarów i zmiana położenia elementów w miejscu.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](class-library-overview.md)
