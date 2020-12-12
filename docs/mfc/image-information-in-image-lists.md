---
description: 'Dowiedz się więcej na temat: informacje o obrazach na listach obrazów'
title: Informacje o obrazach na listach obrazów
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
ms.openlocfilehash: c3a5f1cee0a06177d12b72673bf0ebf8e1a73933
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290144"
---
# <a name="image-information-in-image-lists"></a>Informacje o obrazach na listach obrazów

[Korzystanie CImageList](reference/cimagelist-class.md) zawiera szereg funkcji, które pobierają informacje z listy obrazów. Funkcja członkowska [GetImageInfo](reference/cimagelist-class.md#getimageinfo) wypełnia `IMAGEINFO` strukturę informacjami o pojedynczym obrazie, w tym uchwyty mapy bitowej obrazu i maski, liczbę płaszczyzn kolorów i bitów na piksel oraz obwiednię obrazu w mapie bitowej obrazu. Te informacje służą do bezpośredniego manipulowania mapami bitowymi obrazu.

Funkcja członkowska [GetImageCount](reference/cimagelist-class.md#getimagecount) Pobiera liczbę obrazów z listy obrazów.

Można utworzyć ikonę opartą na obrazie i masce na liście obrazów przy użyciu funkcji składowej [ExtractIcon](reference/cimagelist-class.md#extracticon) . Funkcja zwraca uchwyt nowej ikony.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CImageList](using-cimagelist.md)<br/>
[Formanty](controls-mfc.md)
