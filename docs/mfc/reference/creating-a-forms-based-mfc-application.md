---
description: 'Dowiedz się więcej na temat: Tworzenie aplikacji Forms-Based MFC'
title: Tworzenie aplikacji MFC opartej na formularzach
ms.date: 09/09/2019
f1_keywords:
- vc.appwiz.mfcforms.project
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
ms.openlocfilehash: 2023f4f2c074ef1d0e3adf936cd4c31bd334b795
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343241"
---
# <a name="creating-a-forms-based-mfc-application"></a>Tworzenie aplikacji MFC opartej na formularzach

Formularz to okno dialogowe z kontrolkami, które umożliwiają użytkownikowi dostęp i ewentualnie modyfikowanie danych. Można utworzyć aplikację, w której użytkownik wybiera jeden z wielu formularzy. Zwykle aplikacja oparta na formularzach umożliwia użytkownikowi dostęp do formularzy, klikając pozycję **Nowy** w menu **plik** . Aplikacja oparta na oknach dialogowych, która nie zapewnia użytkownikom dostępu do **nowej** opcji w menu **plik** , jest również traktowana jako aplikacja oparta na formularzach.

Aplikacja oparta na formularzach wykorzystująca mechanizm interfejsu pojedynczego dokumentu (SDI) umożliwia działanie równocześnie tylko jednego wystąpienie danego formularza. Można uruchamiać różne formularze w tym samym czasie z aplikacji opartej na formularzach SDI, wybierając nowy formularz z opcji **Nowy** w menu **plik** .

W przypadku utworzenia aplikacji opartej na formularzach wykorzystującej mechanizm interfejsu wielu dokumentów (MDI) będzie ona obsługiwała wiele wystąpień tego samego formularza.

W aplikacji z obsługą wielu dokumentów najwyższego poziomu niejawnym obiektem nadrzędnym dla dokumentu jest pulpit, a ramka dokumentu nie ogranicza się do obszaru klienckiego aplikacji. Można otworzyć wiele wystąpień dokumentu, każdy z własną ramką, menu i ikoną paska zadań. Kolejne wystąpienia dokumentów można zamknąć pojedynczo, ale w przypadku wybrania opcji **Wyjdź** z menu **plik** początkowego wystąpienia aplikacja zamknie wszystkie wystąpienia.

Aplikacje obsługujące interfejsy SDI i MDI oraz wiele dokumentów najwyższego poziomu są oparte na formularzach i wykorzystują architekturę dokument/widok.

Każda aplikacja oparta na oknach dialogowych jest z definicji oparta na formularzach. Aplikacja oparta na oknach dialogowych nie używa architektury dokument/widok, w związku z czym trzeba zarządzać tworzeniem własnych dodatkowych formularzy i metodami dostępu do nich.

Klasą bazową dla aplikacji opartych na formularzach jest [CFormView](cformview-class.md). Jeśli aplikacja obsługuje bazę danych, można również wybrać dowolną klasę pochodzącą od klasy `CFormView`. Formularzem jest dowolne okno pochodzące od klasy `CFormView` albo od dowolnej klasy dziedziczącej z klasy `CFormView`.

Nawet jeśli używasz klasy bazowej, takiej jak [CView](cview-class.md), możesz później utworzyć aplikacje oparte na formularzach, [dodając klasę MFC](adding-an-mfc-class.md) pochodną `CFormView` .

Po ukończeniu pracy w kreatorze zostanie otwarty projekt. Jeśli jako klasę bazową wybrano `CFormView` (lub klasę dziedziczącą z klasy `CFormView`) lub jeśli utworzono aplikację opartą na oknach dialogowych, zostanie otwarty edytor okien dialogowych. Teraz można przystąpić do projektowania pierwszego formularza.

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>Aby rozpocząć tworzenie pliku wykonywalnego MFC opartego na formularzach

1. Postępuj zgodnie z instrukcjami w temacie [Tworzenie aplikacji MFC](creating-an-mfc-application.md) dla aplikacji MFC opartej na formularzach.

1. Na stronie [Typ aplikacji](application-type-mfc-application-wizard.md) Kreator aplikacji MFC zaznacz pole wyboru **Obsługa architektury dokumentu/widoku** .

1. Zaznacz **pojedynczy dokument**, **wiele dokumentów** lub **wiele dokumentów najwyższego poziomu**.

    > [!NOTE]
    >  Jeśli wybrano aplikację interfejsu SDI, MDI lub wiele dokumentów najwyższego poziomu, domyślnie `CView` jest ona ustawiana jako klasa bazowa widoku aplikacji na stronie [wygenerowane klasy](generated-classes-mfc-application-wizard.md) kreatora. Aby utworzyć aplikację opartą na formularzach, jako klasę bazową widoku aplikacji należy wybrać klasę `CFormView`. Kreator nie zapewnia funkcji drukowania dla aplikacji opartej na formularzach.

1. Na pozostałych stronach kreatora skonfiguruj inne opcje projektu.

1. Kliknij przycisk **Zakończ** , aby wygenerować aplikację szkieletową.

Aby uzyskać więcej informacji, zobacz:

- [Klasy widoków pochodnych](../derived-view-classes-available-in-mfc.md)

- [Alternatywy dla architektury dokumentu/widoku](../alternatives-to-the-document-view-architecture.md)

- [Wybór projektu aplikacji](../application-design-choices.md)

## <a name="see-also"></a>Zobacz też

[Kreator aplikacji MFC](mfc-application-wizard.md)<br/>
[Widoki formularzy](../form-views-mfc.md)<br/>
[Tworzenie pliku Explorer-Style aplikacji MFC](creating-a-file-explorer-style-mfc-application.md)<br/>
[Tworzenie aplikacji sieci Web Browser-Style MFC](creating-a-web-browser-style-mfc-application.md)
