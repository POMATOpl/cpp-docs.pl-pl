---
description: 'Dowiedz się więcej na temat: typ aplikacji, Kreator aplikacji MFC'
title: Typ aplikacji, kreator aplikacji MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.apptype
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
ms.openlocfilehash: 178e9c1319b17e356273fc3e59d2133c8d4aa54c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322788"
---
# <a name="application-type-mfc-application-wizard"></a>Typ aplikacji, kreator aplikacji MFC

Użyj tej strony [Kreatora aplikacji MFC](../../mfc/reference/mfc-application-wizard.md) , aby zaprojektować i dodać podstawowe funkcje do nowej aplikacji MFC.

- **Typ aplikacji**

  Określa typ obsługi dokumentu, który ma zostać utworzony w aplikacji. Wybrany typ aplikacji określa opcje interfejsu użytkownika, które są dostępne dla aplikacji. Aby uzyskać więcej informacji [, zobacz funkcje interfejsu użytkownika, Kreator aplikacji MFC](../../mfc/reference/user-interface-features-mfc-application-wizard.md) .

   Aby uzyskać więcej informacji na temat typów dokumentów, zobacz:

  - [SDI i MDI](../../mfc/sdi-and-mdi.md)

  - [Okna ramowe](../../mfc/frame-windows.md)

  - [Klasy okien ramowych](../../mfc/frame-window-classes.md)

  - [Dokumenty, widoki i struktura](../../mfc/documents-views-and-the-framework.md)

  - [Okna dialogowe](../../mfc/dialog-boxes.md)

  |Opcja|Opis|
  |------------|-----------------|
  |**Pojedynczy dokument**|Tworzy architekturę interfejsu pojedynczego dokumentu (SDI) dla aplikacji, gdzie Klasa widoku jest oparta na [klasie CView](../../mfc/reference/cview-class.md). Możesz zmienić klasę bazową dla widoku na stronie [wygenerowane klasy Kreatora aplikacji MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md) . Aby utworzyć aplikację opartą na formularzach, na przykład użyj [klasy CFormView](../../mfc/reference/cformview-class.md) dla klasy view.<br /><br /> W przypadku tego typu aplikacji okno ramki dokumentu może zawierać tylko jeden dokument.|
  |**Wiele dokumentów**|Tworzy architekturę interfejsu wielu dokumentów (MDI) dla aplikacji, w której jest oparta Klasa widoku `CView` . Można zmienić klasę bazową widoku na stronie **wygenerowane klasy** kreatora. Aby utworzyć aplikację opartą na formularzach, na przykład, użyj `CFormView` klasy view.<br /><br /> W przypadku tego typu aplikacji okno ramki dokumentu może zawierać wiele okien podrzędnych.|
  |**Dokumenty z kartami**|Umieszcza każdy dokument na osobnej karcie.|
  |**Na podstawie okna dialogowego**|Tworzy architekturę opartą na oknach dialogowych dla aplikacji, w której jest oparta Klasa okna dialogowego `CDialog` . (Aby utworzyć okno dialogowe HTML, zaznacz pole wyboru **Użyj okna dialogowego HTML**.)|
  |**Korzystanie z okna dialogowego HTML**|Tylko dla aplikacji okna dialogowego. Dziedziczy klasę okna dialogowego z [klasy CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) zamiast [klasy CDialog](../../mfc/reference/cdialog-class.md). Jeśli to pole wyboru jest zaznaczone, `CDHtmlDialog` jest wyświetlane w polu **Klasa podstawowa** na stronie [wygenerowane klasy Kreatora aplikacji MFC](../../mfc/reference/generated-classes-mfc-application-wizard.md) .<br /><br /> Okno `CDHtmlDialog` dialogowe pochodne wyświetla okna dialogowe oparte na języku HTML, wymienia dane z kontrolkami HTML i obsługuje zdarzenia html.|
  |**Wiele dokumentów najwyższego poziomu**|Tworzy wiele architektury najwyższego poziomu dla aplikacji, w której jest oparta Klasa widoku `CView` .<br /><br /> W przypadku tego typu aplikacji, gdy użytkownik kliknie **nową** (lub **nową ramkę**) w menu **plik** , aplikacja tworzy okno, którego element nadrzędny jest niejawnie pulpitem. Nowa ramka dokumentu pojawia się na pasku zadań i nie jest ograniczona do obszaru klienckiego okna aplikacji.|

- **Obsługa architektury dokumentu/widoku**

  Określa, czy uwzględnić architekturę dokumentu/widoku w aplikacji za pomocą [klasy CDocument](../../mfc/reference/cdocument-class.md) i [klasy CView](../../mfc/reference/cview-class.md) (domyślnie). Wyczyść to pole wyboru, jeśli zamierzasz przenieść aplikację nie będącą MFC lub chcesz zmniejszyć rozmiar skompilowanego pliku wykonywalnego. Domyślnie aplikacja bez architektury Document/View jest pochodną [klasy CWinApp](../../mfc/reference/cwinapp-class.md)i nie obejmuje ona obsługi MFC otwierającej dokument z pliku dyskowego.

- **Język zasobów**

  Ustawia język zasobów. Na liście wyświetlane są języki dostępne w systemie, które są instalowane przez program Visual Studio. Jeśli chcesz wybrać język inny niż język systemu, musi być już zainstalowany odpowiedni folder szablonu dla tego języka.

  Wybrany język jest widoczny w opcji **zlokalizowane ciągi** w kreatorze [szablonu dokumentu, stronie Kreatora aplikacji MFC](../../mfc/reference/document-template-strings-mfc-application-wizard.md) .

- **Korzystanie z bibliotek Unicode**

  Określa, czy używane są wersje Unicode lub inne niż Unicode bibliotek MFC.

- **Styl projektu**

  Wskazuje, czy aplikacja ma Standard MFC, Eksploratora plików, Visual Studio lub architekturę pakietu Office i wyświetla. Aby uzyskać więcej informacji, zobacz [Tworzenie pliku Explorer-Style aplikacji MFC](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md).

  |Opcja|Opis|
  |------------|-----------------|
  |**Standard MFC**|Zapewnia standardową architekturę aplikacji MFC.|
  |**Eksplorator plików**|Implementuje aplikację podobną do Eksploratora plików przy użyciu okna rozdzielacza, w którym lewe okienko jest [klasą CTreeView](../../mfc/reference/ctreeview-class.md) , a prawego okienka jest [klasą CListView](../../mfc/reference/clistview-class.md).|
  |**Program Visual Studio**|Implementuje aplikację podobną do programu Visual Studio, która zawiera cztery okienka było dokować (**Widok pliku**, **Widok klasy**, **Właściwości** i **dane wyjściowe**), które są wyprowadzane z [klasy CDockablePane](../../mfc/reference/cdockablepane-class.md) i głównego okna ramowego pochodnego od [klasy CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md) (domyślnie).|
  |**Office**|Implementuje aplikację podobną do pakietu Office, która zawiera wstążkę utworzoną z [klasy CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md), pasek programu Outlook pochodzący z [klasy CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md), pasek podpisu pochodzący z [klasy CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)i główną ramkę pochodną [klasy CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md).|

- **Styl wizualny i kolory**

  Określa styl wizualizacji aplikacji. Dostępne są następujące opcje:

  - **Natywny/domyślny dla systemu Windows**

  - **Pakiet Office 2003**

  - **Visual Studio 2005**

  - **Office 2007 (motyw niebieski)**

  - **Office 2007 (motyw czarny)**

  - **Office 2007 (motyw Silver)**

  - **Office 2007 (motyw akwamaryna)**

- **Włącz przełączanie stylu wizualnego**

  Określa, czy użytkownik może zmienić styl wizualizacji aplikacji w czasie wykonywania, zazwyczaj poprzez wybranie odpowiedniego stylu wizualizacji z menu lub wstążki.

- **Użycie MFC**

  Określa sposób łączenia z biblioteką MFC. Domyślnie MFC jest połączone jako udostępniona biblioteka DLL.

  |Opcja|Opis|
  |------------|-----------------|
  |**Używanie MFC w udostępnionej bibliotece DLL**|Łączy bibliotekę MFC z aplikacją jako udostępnioną biblioteką DLL. Aplikacja wykonuje wywołania do biblioteki MFC w czasie wykonywania. Ta opcja zmniejsza wymagania dotyczące dysku i pamięci aplikacji, które składają się z wielu plików wykonywalnych korzystających z biblioteki MFC. Aplikacje Win32 i MFC mogą wywoływać funkcje w bibliotece DLL (wartość domyślna)|
  |**Używanie MFC w bibliotece statycznej**|Łączy aplikację ze statyczną biblioteką MFC w czasie kompilacji.|

## <a name="see-also"></a>Zobacz też

[Kreator aplikacji MFC](../../mfc/reference/mfc-application-wizard.md)<br/>
[Typy plików utworzone dla projektów Visual Studio C++](../../build/reference/file-types-created-for-visual-cpp-projects.md)
