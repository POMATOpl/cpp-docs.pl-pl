---
description: 'Dowiedz się więcej na temat: Kreator kontrolek ActiveX MFC'
title: Kreator formantów MFC ActiveX
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.mfc.ctl.overview
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
ms.openlocfilehash: f313f2a218c06a20eddbfff33e936109e4be2cf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219268"
---
# <a name="mfc-activex-control-wizard"></a>Kreator formantów MFC ActiveX

Kontrolka ActiveX jest określonym typem [serwera automatyzacji](../../mfc/automation-servers.md); jest to składnik wielokrotnego użytku. Aplikacja hostującym formant ActiveX jest [klientem automatyzacji](../../mfc/automation-clients.md) tej kontrolki. Jeśli chcesz utworzyć taki składnik wielokrotnego użytku, użyj tego kreatora, aby utworzyć formant. Aby uzyskać więcej informacji, zobacz [kontrolki ActiveX MFC](../../mfc/mfc-activex-controls.md) .

>[!IMPORTANT]
> Kontrolka ActiveX to Starsza technologia, która nie powinna być używana do nowych celów programistycznych. Aby uzyskać więcej informacji na temat nowoczesnych technologii, które zastępują ActiveX, zobacz [kontrolki ActiveX](../activex-controls.md).

Alternatywnie można utworzyć aplikację MFC serwera automatyzacji za pomocą [Kreatora aplikacji MFC](../../mfc/reference/mfc-application-wizard.md).

Formant ActiveX utworzony za pomocą tego kreatora może mieć interfejs użytkownika lub może być niewidoczny. Tę opcję można wskazać na stronie [Ustawienia kontroli](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) w kreatorze. Kontrolka Timer to przykład kontrolki ActiveX, która ma być niewidoczna.

Formanty ActiveX mogą mieć złożony interfejs użytkownika. Niektóre kontrolki mogą przypominać formularze hermetyzowane: pojedyncza kontrolka zawierająca wiele pól, każda kontrolka systemu Windows we własnym zakresie. Na przykład obiekt Autopart zaimplementowany jako formant ActiveX MFC może stanowić interfejs użytkownika przypominający formularz, za pomocą którego użytkownicy mogą odczytywać i edytować numer części, nazwę części i inne informacje. Aby uzyskać więcej informacji, zobacz [kontrolki ActiveX MFC](../../mfc/mfc-activex-controls.md) .

Jeśli musisz utworzyć kontener dla obiektów ActiveX, zobacz [Tworzenie kontenera kontrolki ActiveX](../../mfc/reference/creating-an-mfc-activex-control-container.md).

Program Starter MFC zawiera pliki źródłowe (. cpp) języka C++, pliki zasobów (. RC) i plik projektu (. vcxproj). Kod wygenerowany w tych starterach plików jest oparty na MFC.

Poniższa lista Przykładowa zawiera zadania i typy ulepszeń dla kontrolki ActiveX:

- [Optymalizowanie kontrolki ActiveX](../../mfc/mfc-activex-controls-optimization.md)

- [Dodawanie zdarzeń giełdowych do kontrolki ActiveX](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [Dodawanie niestandardowych zdarzeń](../../mfc/mfc-activex-controls-adding-custom-events.md)

- [Dodawanie metod podstawowych](../../mfc/mfc-activex-controls-adding-stock-methods.md)

- [Dodawanie metod niestandardowych](../../mfc/mfc-activex-controls-adding-custom-methods.md)

- [Dodawanie właściwości podstawowych](../../mfc/mfc-activex-controls-adding-stock-properties.md)

- [Dodawanie właściwości niestandardowych](../../mfc/mfc-activex-controls-adding-custom-properties.md)

- [Programowanie formantów ActiveX w kontenerze kontrolek ActiveX](../../mfc/programming-activex-controls-in-a-activex-control-container.md)

## <a name="overview"></a>Omówienie

Ta strona kreatora zawiera opis bieżących ustawień aplikacji dla tworzonego projektu kontrolki ActiveX MFC. Domyślnie kreator tworzy projekt w następujący sposób:

- Projekt domyślny nie generuje licencji w czasie wykonywania ani plików pomocy. Te ustawienia domyślne można zmienić na stronie [Ustawienia aplikacji](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) . Na stronie **Przegląd** zostaną odzwierciedlone tylko wybrane opcje na tej stronie kreatora kontrolek ActiveX.

- Projekt zawiera klasę formantów i klasę strony właściwości na podstawie nazwy projektu. Nazwy projektu i nazwy plików można edytować na stronie [nazw kontrolek](../../mfc/reference/control-names-mfc-activex-control-wizard.md) .

- Formant jest oparty na żadnej z istniejących kontrolek systemu Windows, uaktywnia się, gdy staną się widoczne, ma interfejs użytkownika i zawiera okno dialogowe **informacje** . Te ustawienia domyślne można zmienić na stronie [Ustawienia kontrolek](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) .

## <a name="see-also"></a>Zobacz też

[Projekty programu Visual Studio — C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[Typy projektów C++ w programie Visual Studio](../../build/reference/visual-cpp-project-types.md)<br/>
[Pojęcia](../../atl/active-template-library-atl-concepts.md)
