---
description: 'Dowiedz się więcej na temat: Kreator okna dialogowego ATL'
title: Kreator okna dialogowego ATL
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
ms.openlocfilehash: 2fc110f12399c0c855cb98a9d7e505180bef7b0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158884"
---
# <a name="atl-dialog-wizard"></a>Kreator okna dialogowego ATL

Ten Kreator wstawia do projektu obiekt okna dialogowego ATL, pochodzący od [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Okno dialogowe pochodne `CAxDialogImpl` może hostować kontrolki ActiveX.

Kreator tworzy zasób okna dialogowego z domyślnymi przyciskami **OK** i **Anuluj** . Można edytować zasób okna dialogowego i dodać kontrolki ActiveX przy użyciu [edytora okien dialogowych](../../windows/dialog-editor.md) w Widok zasobów.

Kreator wstawia do pliku nagłówkowego [mapę komunikatów](../../atl/message-maps-atl.md) i deklaracje służące do obsługi domyślnych zdarzeń kliknięcia. Zobacz [implementowanie okna dialogowego,](../../atl/implementing-a-dialog-box.md) Aby uzyskać więcej informacji o oknach dialogowych ATL.

- **Krótka nazwa**

   Ustawia skróconą nazwę dla obiektu okna dialogowego ATL. Wprowadzona nazwa określa nazwę klasy i nazwy plików (. cpp i. h), chyba że te pola są zmieniane pojedynczo.

- **Klasa**

   Ustawia nazwę klasy, która ma zostać utworzona. Ta nazwa jest oparta na nazwie podanym w **skrócie nazwa**, poprzedzona znakiem "C", typowym prefiksem dla nazwy klasy.

- **plik h**

   Ustawia nazwę pliku nagłówka dla klasy nowego obiektu. Domyślnie ta nazwa jest oparta na nazwie podanym w polu **krótka nazwa**. Kliknij przycisk wielokropka, aby zapisać nazwę pliku w wybranej lokalizacji, lub dołączyć deklarację klasy do istniejącego pliku. Jeśli wybierzesz istniejący plik, Kreator nie zapisze go w wybranej lokalizacji, dopóki nie klikniesz przycisku **Zakończ** w kreatorze.

   Kreator nie zastępuje pliku. Jeśli wybierzesz nazwę istniejącego pliku, po kliknięciu przycisku **Zakończ** Kreator monituje o wskazanie, czy deklaracja klasy powinna zostać dołączona do zawartości pliku. Kliknij przycisk **tak** , aby dołączyć plik; Kliknij przycisk **nie** , aby powrócić do kreatora i określić inną nazwę pliku.

- **plik. cpp**

   Ustawia nazwę pliku implementacji dla klasy nowego obiektu. Domyślnie ta nazwa jest oparta na nazwie podanym w polu **krótka nazwa**. Kliknij przycisk wielokropka, aby zapisać nazwę pliku w wybranej lokalizacji. Plik nie jest zapisywany w wybranej lokalizacji, dopóki nie zostanie kliknięty przycisk **Zakończ** w kreatorze.

   Kreator nie zastępuje pliku. W przypadku wybrania nazwy istniejącego pliku po kliknięciu przycisku **Zakończ** Kreator monituje o wskazanie, czy implementacja klasy powinna zostać dołączona do zawartości pliku. Kliknij przycisk **tak** , aby dołączyć plik; Kliknij przycisk **nie** , aby powrócić do kreatora i określić inną nazwę pliku.

## <a name="see-also"></a>Zobacz też

[ATL — okno dialogowe](../../atl/reference/adding-an-atl-dialog-box.md)
