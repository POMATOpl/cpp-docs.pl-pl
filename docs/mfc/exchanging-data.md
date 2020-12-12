---
description: Dowiedz się więcej o tym, jak wymieniać dane
title: Wymiana danych
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
ms.openlocfilehash: 9163434d51e3fa248f858434aece8f420e63197d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290452"
---
# <a name="exchanging-data"></a>Wymiana danych

Podobnie jak w przypadku większości okien dialogowych, wymiana danych między arkuszem właściwości a aplikacją jest jedną z najważniejszych funkcji arkusza właściwości. W tym artykule opisano, jak wykonać to zadanie.

Wymiana danych z arkuszem właściwości jest w rzeczywistości kwestią wymiany danych przy użyciu poszczególnych stron właściwości arkusza właściwości. Procedura wymiany danych ze stroną właściwości jest taka sama jak w przypadku wymiany danych przy użyciu okna dialogowego, ponieważ obiekt [CPropertyPage](reference/cpropertypage-class.md) jest tylko wyspecjalizowanym obiektem [CDialog](reference/cdialog-class.md) . Procedura korzysta z funkcji wymiany danych okna dialogowego (DDX) struktury, która wymienia dane między kontrolkami w oknie dialogowym a zmiennymi składowymi obiektu okna dialogowego.

Istotną różnicą między wymianą danych a arkuszem właściwości i normalnym oknem dialogowym jest to, że arkusz właściwości ma wiele stron, dlatego należy wymienić dane ze wszystkimi stronami w arkuszu właściwości. Aby uzyskać więcej informacji na temat DDX, zobacz temat [wymiana i walidacja danych w oknie dialogowym](dialog-data-exchange-and-validation.md).

Poniższy przykład ilustruje wymianę danych między widokiem a dwiema stronami arkusza właściwości:

[!code-cpp[NVC_MFCDocView#4](codesnippet/cpp/exchanging-data_1.cpp)]

## <a name="see-also"></a>Zobacz też

[Arkusze właściwości](property-sheets-mfc.md)
