---
description: 'Dowiedz się więcej o: nakładki obrazów na listach obrazów'
title: Nakładki obrazów na listach obrazów
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: dd65a27c9ef66311311195c1493e91be8c66d100
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290118"
---
# <a name="image-overlays-in-image-lists"></a>Nakładki obrazów na listach obrazów

Każda lista obrazów ([Korzystanie CImageList](reference/cimagelist-class.md)) zawiera listę obrazów do użycia jako maski nakładki. "Maska nakładki" to obraz rysowany w sposób przezroczysty na innym obrazie. Dowolny obraz może być używany jako maska nakładki. Można określić maksymalnie cztery maski nakładania na listę obrazów.

Indeks obrazu można dodać do listy masek nakładki przy użyciu funkcji składowej [SetOverlayImage](reference/cimagelist-class.md#setoverlayimage) , indeksu obrazu oraz indeksu maski nakładki. Należy zauważyć, że indeksy dla masek nakładki są oparte na jednym, a nie na podstawie zera.

Narysujmy maskę nakładki na obrazie przy użyciu jednego wywołania do `Draw` . Parametry obejmują indeks obrazu do rysowania i indeks maski nakładki. Aby określić indeks maski nakładki, należy użyć makra [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) . Możesz również określić obraz nakładki podczas wywoływania funkcji składowej [DrawIndirect](reference/cimagelist-class.md#drawindirect) .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CImageList](using-cimagelist.md)<br/>
[Formanty](controls-mfc.md)
