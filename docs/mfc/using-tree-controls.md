---
description: 'Dowiedz się więcej na temat: używanie kontrolek drzewa'
title: Używanie kontrolek drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
ms.openlocfilehash: 7b8a10acc3ee256f4b26c9988c4de7df900e1535
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143198"
---
# <a name="using-tree-controls"></a>Używanie kontrolek drzewa

Typowym użyciem formantu drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) jest Poniższy wzorzec:

- Formant zostanie utworzony. Jeśli formant jest określony w szablonie okna dialogowego lub jeśli używasz `CTreeView` , tworzenie jest automatyczne podczas tworzenia okna dialogowego lub widoku. Jeśli chcesz utworzyć formant drzewa jako okno podrzędne innego okna, użyj funkcji [tworzenia](../mfc/reference/ctreectrl-class.md#create) elementu członkowskiego.

- Jeśli chcesz, aby kontrolka drzewa korzystała z obrazów, Ustaw listę obrazów, wywołując metodę [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist). Możesz również zmienić wcięcia, wywołując metodę [setwcięcie](../mfc/reference/ctreectrl-class.md#setindent). Dobrym terminem jest to, że jest to [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (dla kontrolek w oknach dialogowych) lub [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (dla widoków).

- Umieść dane w kontrolce, wywołując `CTreeCtrl` funkcję [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) raz dla każdego elementu danych. `InsertItem` zwraca dojście do elementu, którego można użyć do późniejszego odwoływania się do niego, na przykład podczas dodawania elementów podrzędnych. Dobry czas na zainicjowanie danych to `OnInitDialog` (dla kontrolek w oknach dialogowych) lub `OnInitialUpdate` (dla widoków).

- Gdy użytkownik współdziała z kontrolką, wyśle różne komunikaty powiadomień. Możesz określić funkcję obsługującą poszczególne komunikaty, które chcesz obsłużyć, dodając ON_NOTIFY_REFLECT makro w mapie komunikatów okna kontrolki lub dodając makro ON_NOTIFY do mapy komunikatów okna nadrzędnego. Listę możliwych powiadomień można znaleźć w sekcji [komunikaty powiadomień drzewa](../mfc/tree-control-notification-messages.md) w dalszej części tego tematu.

- Wywołaj różne funkcje zestawu elementów członkowskich, aby ustawić wartości dla kontrolki. Zmiany, które można wprowadzić, obejmują ustawienie wcięcia i zmianę tekstu, obrazu lub danych skojarzonych z elementem.

- Użyj różnych funkcji get do sprawdzenia zawartości kontrolki. Można również przechodzenie przez zawartość kontrolki drzewa przy użyciu funkcji, które umożliwiają pobieranie dojść do elementów nadrzędnych, podrzędnych i elementów równorzędnych określonego elementu. Można nawet posortować elementy podrzędne określonego węzła.

- Po zakończeniu pracy z kontrolką upewnij się, że jest prawidłowo zniszczona. Jeśli formant drzewa znajduje się w oknie dialogowym lub jest widokiem, a `CTreeCtrl` obiekt zostanie zniszczony automatycznie. Jeśli nie, musisz upewnić się, że zarówno kontrolka, jak i `CTreeCtrl` obiekt są prawidłowo niszczone.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
