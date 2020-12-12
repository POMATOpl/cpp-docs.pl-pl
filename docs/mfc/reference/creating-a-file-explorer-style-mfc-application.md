---
description: 'Dowiedz się więcej o: Tworzenie pliku Explorer-Style aplikacji MFC'
title: Tworzenie aplikacji MFC w stylu eksploratora plików
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcexplorer.project
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
ms.openlocfilehash: 9419aae58cf34ec70585b952360cb12702424381
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301324"
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>Tworzenie aplikacji MFC w stylu eksploratora plików

Wiele aplikacji systemu Windows korzysta z interfejsu użytkownika (UI) dla Eksploratora plików. Po uruchomieniu Eksploratora plików, na przykład, zobaczysz aplikację z pionowym paskiem podziału dzielącym obszar klienta. Po lewej stronie obszaru klienta dostępne są funkcje nawigacji i przeglądania, a po prawej stronie obszaru klienta wyświetlane są szczegółowe informacje dotyczące wyboru w lewym okienku. Gdy użytkownik kliknie element w okienku po lewej stronie, aplikacja ponownie wypełni odpowiednie okienko. W aplikacji MDI można użyć poleceń z menu **Widok** , aby zmienić ilość szczegółów wyświetlanych w okienku po prawej stronie. (W pliku SDI lub wielu aplikacjach najwyższego poziomu można zmienić szczegóły, korzystając tylko z przycisków paska narzędzi).

Zawartość okienek jest zależna od aplikacji. W przeglądarce systemu plików w okienku po lewej stronie jest wyświetlany hierarchiczny widok katalogów lub maszyn lub grup maszyn, podczas gdy w okienku po prawej stronie są wyświetlane foldery, pojedyncze pliki lub maszyny i szczegółowe informacje o nich. Zawartość nie musi być plików. Mogą one być wiadomościami e-mail, raportami o błędach lub innymi elementami w bazie danych.

Kreator tworzy następujące klasy:

- `CLeftView`Klasa definiuje lewe okienko w obszarze klienta. Jest on zawsze wyprowadzany z [CTreeView](../../mfc/reference/ctreeview-class.md).

- Kategoria widoku C *Projname* definiuje odpowiednie okienko w obszarze klienta. Domyślnie jest on tworzony z [CListView](../../mfc/reference/clistview-class.md) , ale może być innym typem widoku w zależności od klasy określonej przez użytkownika z listy **klas podstawowych** na stronie [wygenerowane klasy](../../mfc/reference/generated-classes-mfc-application-wizard.md) kreatora.

Wygenerowana aplikacja może mieć interfejs pojedynczego dokumentu (SDI), interfejs wielu dokumentów (MDI) lub wiele dokumentów najwyższego poziomu. Każde okno ramki tworzone przez aplikację jest podzielone pionowo przy użyciu [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md). Kodowanie tego typu aplikacji jest podobne do kodowania normalnej aplikacji MFC, która używa rozdzielacza, z tą różnicą, że ten typ aplikacji ma oddzielne widoki kontroli w poszczególnych okienkach rozdzielacza.

Jeśli w okienku po prawej stronie jest używany domyślny widok listy, Kreator tworzy dodatkowe opcje menu (tylko w aplikacjach MDI) i przyciski paska narzędzi, aby przełączać styl widoku między dużymi ikonami, małymi ikonami, listą i trybami szczegółów.

### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>Aby rozpocząć tworzenie pliku wykonywalnego MFC w stylu Eksploratora plików

1. Postępuj zgodnie z instrukcjami w temacie [Tworzenie aplikacji MFC](../../mfc/reference/creating-an-mfc-application.md).

1. Na stronie [Typ aplikacji](../../mfc/reference/application-type-mfc-application-wizard.md) Kreator aplikacji MFC wybierz styl projektu **Eksploratora plików** .

1. Ustaw dowolne inne opcje na innych stronach kreatora.

1. Kliknij przycisk **Zakończ** , aby wygenerować aplikację szkieletową.

Aby uzyskać więcej informacji, zobacz:

- [Wiele typów dokumentów, widoków i okien ramowych](../../mfc/multiple-document-types-views-and-frame-windows.md)

- [Klasy widoków pochodnych](../../mfc/derived-view-classes-available-in-mfc.md)

- [Wybór projektu aplikacji](../../mfc/application-design-choices.md)

## <a name="see-also"></a>Zobacz też

[Kreator aplikacji MFC](../../mfc/reference/mfc-application-wizard.md)<br/>
[Tworzenie aplikacji sieci Web Browser-Style MFC](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)<br/>
[Tworzenie Forms-Based aplikacji MFC](../../mfc/reference/creating-a-forms-based-mfc-application.md)
