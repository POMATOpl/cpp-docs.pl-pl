---
description: 'Dowiedz się więcej na temat: style kontrolki postępu'
title: Style formantu postępu
ms.date: 11/19/2018
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
ms.openlocfilehash: cd6ce1093f8bd2e3271a386e894d1e8dcd1a4fd7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216499"
---
# <a name="styles-for-the-progress-control"></a>Style formantu postępu

Gdy początkowo tworzysz kontrolkę postępu ([Korzystanie CProgressCtrl:: Create](../mfc/reference/cprogressctrl-class.md#create)), użyj parametru *dwStyle* , aby określić żądane style okna dla kontrolki postępu. Poniższa lista zawiera szczegółowe informacje dotyczące odpowiednich stylów okna. Formant ignoruje wszystkie style okna inne niż wymienione w tym miejscu. Kontrolkę należy zawsze tworzyć jako okno podrzędne, zazwyczaj z poziomu nadrzędnego okna dialogowego.

|Styl okna|Efekt|
|------------------|------------|
|WS_BORDER|Tworzy obramowanie wokół okna.|
|WS_CHILD|Tworzy okno podrzędne (powinno być zawsze używane do `CProgressCtrl` ).|
|WS_CLIPCHILDREN|Wyklucza obszar zajęty przez okna podrzędne podczas rysowania w oknie nadrzędnym. Używane podczas tworzenia okna nadrzędnego.|
|WS_CLIPSIBLINGS|Powoduje, że podrzędne okna są zależne od siebie.|
|WS_DISABLED|Tworzy okno, które jest początkowo wyłączone.|
|WS_VISIBLE|Tworzy okno, które jest początkowo widoczne.|
|WS_TABSTOP|Określa, że kontrolka może odbierać fokus, gdy użytkownik naciśnie klawisz TAB, aby przejść do niego.|

Ponadto można określić dwa style, które mają zastosowanie tylko do kontrolki postępu, PBS_VERTICAL i PBS_SMOOTH.

Użyj PBS_VERTICAL, aby określić orientację w pionie, a nie w poziomie. Użyj PBS_SMOOTH, aby całkowicie wypełnić formant, zamiast wyświetlać małe rozdzielone kwadraty wypełniające formant przyrostowo.

Bez PBS_SMOOTH stylu:

![Standardowy styl paska postępu](../mfc/media/vc4ruw1.gif "Standardowy styl paska postępu")

Ze stylami PBS_SMOOTH i PBS_VERTICAL:

![Styl paska postępu, gładki i pionowy](../mfc/media/vc4ruw2.gif "Styl paska postępu, gładki i pionowy")

Aby uzyskać więcej informacji, zobacz [Style okna](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) w *dokumentacji MFC*.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CProgressCtrl](../mfc/using-cprogressctrl.md)
