---
description: 'Dowiedz się więcej o programie: Zarządzanie bieżącym widokiem'
title: Zarządzanie bieżącym widokiem
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], and OnActivateView method [MFC]
- views [MFC], deactivating
- views [MFC], activating
- frame windows [MFC], current view
- OnActivateView method [MFC]
- views [MFC], current
- deactivating views [MFC]
- current view in frame window [MFC]
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
ms.openlocfilehash: 9c9acd315636ea33c52fbe63374b5afacef95247
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283345"
---
# <a name="managing-the-current-view"></a>Zarządzanie bieżącym widokiem

W ramach domyślnej implementacji okien ramowych, okno ramki śledzi aktualnie aktywny widok. Jeśli okno ramki zawiera więcej niż jeden widok, jak na przykład w oknie rozdzielacza bieżący widok jest ostatnim widokiem w użyciu. Aktywny widok jest niezależny od aktywnego okna w systemie Windows lub bieżącego fokusu wprowadzania.

Gdy aktywny widok zostanie zmieniony, struktura powiadamia bieżący widok, wywołując jego funkcję członkowską [OnActivateView](reference/cview-class.md#onactivateview) . Możesz sprawdzić, czy widok jest aktywowany, czy zdezaktywowany, badając `OnActivateView` parametr *bActivate* . Domyślnie program `OnActivateView` Ustawia fokus na bieżący widok podczas aktywacji. Można przesłonić `OnActivateView` w celu przeprowadzenia dowolnego przetwarzania specjalnego, gdy widok zostanie zdezaktywowany lub ponownie aktywowany. Na przykład możesz chcieć podać specjalne podpowiedzi wizualne do odróżnienia aktywnego widoku od innych nieaktywnych widoków.

Okno ramowe przekazuje polecenia do bieżącego (aktywnego) widoku, zgodnie z opisem w temacie [routing poleceń](command-routing.md)w ramach standardowego routingu poleceń.

## <a name="see-also"></a>Zobacz też

[Korzystanie z okien ramowych](using-frame-windows.md)
