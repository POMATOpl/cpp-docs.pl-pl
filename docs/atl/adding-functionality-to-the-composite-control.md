---
description: 'Dowiedz się więcej na temat: Dodawanie funkcji do kontrolki złożonej'
title: Dodawanie funkcji do kontrolki złożonej
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 90e1f6b0adfc33817f9fa5a6de6fbdcd276241e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166125"
---
# <a name="adding-functionality-to-the-composite-control"></a>Dodawanie funkcji do kontrolki złożonej

Po wstawieniu wszelkich niezbędnych kontrolek do kontrolki złożonej następny krok obejmuje dodanie nowej funkcji. Ta nowa funkcja zwykle znajduje się w dwóch kategoriach:

- Obsługa dodatkowych interfejsów i Dostosowywanie zachowania kontroli złożonej przy użyciu dodatkowych, określonych funkcji.

- Obsługa zdarzeń z zawartej kontrolki ActiveX (lub kontrolek).

Do celów i zakresu tego artykułu w pozostałej części tej sekcji omówiono wyłącznie obsługę zdarzeń z formantów ActiveX.

> [!NOTE]
> Jeśli musisz obsługiwać komunikaty z formantów systemu Windows, zobacz [implementowanie okna](../atl/implementing-a-window.md) , aby uzyskać więcej informacji na temat obsługi komunikatów w ATL.

Po wstawieniu kontrolki ActiveX w zasobie okna dialogowego kliknij prawym przyciskiem myszy formant i kliknij polecenie **Dodaj obsługę zdarzeń**. Wybierz zdarzenie, które chcesz obsłużyć, a następnie kliknij przycisk **Dodaj i edytuj**. Kod procedury obsługi zdarzeń zostanie dodany do pliku. h formantu.

Punkty połączenia dla kontrolek ActiveX w formancie złożonym są automatycznie połączone i rozłączone przez wywołania do [CComCompositeControl:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

## <a name="see-also"></a>Zobacz też

[Podstawy kontroli złożonej](../atl/atl-composite-control-fundamentals.md)
