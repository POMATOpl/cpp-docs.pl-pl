---
description: 'Dowiedz się więcej na temat: kreatorów i edytorów zasobów'
title: Kreatorzy i edytory zasobów
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and MFC
- MFC, resource editors
- resource editors, MFC
- MFC Application Wizard
- editors [MFC], resource
- wizards [MFC]
- wizards [MFC], MFC programming
- MFC, wizards
- Class View tool, managing Windows messages
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
ms.openlocfilehash: b493746365809ca6fd193a31d0e7f53917a9646f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284918"
---
# <a name="wizards-and-the-resource-editors"></a>Kreatorzy i edytory zasobów

Visual C++ obejmuje kilka kreatorów używanych w programowaniu MFC oraz wielu zintegrowanych edytorów zasobów. W przypadku formantów ActiveX, [Kreator kontrolek ActiveX](../mfc/reference/mfc-activex-control-wizard.md) służy do celów, podobnie jak w Kreatorze aplikacji MFC. Chociaż możesz pisać aplikacje MFC bez większości tych narzędzi, narzędzia znacznie upraszczają i przyspieszają pracę.

## <a name="use-the-mfc-application-wizard-to-create-an-mfc-application"></a><a name="_core_use_appwizard_to_create_an_mfc_application"></a> Tworzenie aplikacji MFC przy użyciu Kreatora aplikacji MFC

Użyj [Kreatora aplikacji MFC](../mfc/reference/mfc-application-wizard.md) , aby utworzyć projekt mfc w Visual C++, który może obejmować obsługę OLE i bazy danych. Pliki w projekcie zawierają klasy aplikacji, dokumentów, widoków i okien ramowych; zasoby standardowe, w tym menu i opcjonalny pasek narzędzi; inne wymagane pliki systemu Windows; i opcjonalne pliki. rtf zawierające standardowe tematy pomocy systemu Windows, które można skorygować i rozszerzyć, aby utworzyć plik pomocy programu.

## <a name="use-class-view-to-manage-classes-and-windows-messages"></a><a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> Używanie Widok klasy do zarządzania klasami i komunikatami systemu Windows

Widok klasy ułatwia tworzenie funkcji obsługi dla komunikatów i poleceń systemu Windows, tworzenie klas i zarządzanie nimi, Tworzenie zmiennych składowych klasy, Tworzenie metod automatyzacji i właściwości, tworzenie klas baz danych i nie tylko.

> [!NOTE]
> Widok klasy również pomaga przesłonić funkcje wirtualne w klasach MFC. Wybierz klasę i funkcję wirtualną, która ma zostać przesłonięta. Pozostała część tego procesu jest podobna do obsługi komunikatów, zgodnie z opisem w poniższych akapitach.

Aplikacje działające w systemie Windows są [sterowane komunikatami](../mfc/message-handling-and-mapping.md). Akcje użytkownika i inne zdarzenia występujące w uruchomionym programie powodują, że system Windows wyśle komunikaty do systemu Windows w programie. Na przykład jeśli użytkownik kliknie myszą w oknie, system Windows wyśle komunikat WM_LBUTTONDOWN po naciśnięciu lewego przycisku myszy, a komunikat WM_LBUTTONUP po wydaniu przycisku. System Windows wysyła również komunikaty WM_COMMAND, gdy użytkownik wybierze polecenia z paska menu.

W strukturze MFC, różne obiekty, takie jak dokumenty, widoki, okna ramowe, szablony dokumentów i obiekt aplikacji, mogą "obsługiwać" komunikatów. Taki obiekt udostępnia "funkcję obsługi" jako jedną z jej funkcji składowych, a struktura mapuje komunikat przychodzący do procedury obsługi.

Duża część zadania programistycznego polega na wybraniu komunikatów do mapowania obiektów, a następnie implementowania tego mapowania. W tym celu należy użyć Widok klasy i [kreatora klas](reference/mfc-class-wizard.md).

[Kreator klas](reference/mfc-class-wizard.md) utworzy puste funkcje członkowskie programu obsługi komunikatów i użyje edytora kodu źródłowego do zaimplementowania treści programu obsługi. Można również tworzyć lub edytować klasy (w tym klasy własne, niepochodzące od klas MFC) i ich członków za pomocą Widok klasy. Aby uzyskać więcej informacji na temat używania Widok klasy i kreatorów, które dodają kod do projektu, zobacz [Dodawanie funkcji za pomocą kreatorów kodu](../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="use-the-resource-editors-to-create-and-edit-resources"></a><a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> Tworzenie i edytowanie zasobów przy użyciu edytorów zasobów

Za pomocą [edytorów zasobów](../windows/resource-editors.md) Visual C++ można tworzyć i edytować menu, okna dialogowe, kontrolki niestandardowe, klawisze skrótów, mapy bitowe, ikony, kursory, ciągi i zasoby wersji. Począwszy od Visual C++ w wersji 4,0, Edytor paska narzędzi znacznie ułatwia tworzenie pasków narzędzi.

Aby jeszcze bardziej pomóc, biblioteka MFC udostępnia plik o nazwie COMMON. RES, która zawiera zasoby "clipart", które można skopiować ze wspólnego. RES i wklej do własnego pliku zasobów. Wspólna. ZASÓB zawiera przyciski paska narzędzi, typowe kursory, ikony i inne. W aplikacji można używać, modyfikować i rozpowszechniać te zasoby. Aby uzyskać więcej informacji o typowych. RES, zobacz [przykład clipart](../overview/visual-cpp-samples.md).

Kreator aplikacji MFC, kreatory Visual C++, edytory zasobów i platforma MFC nie wykonują dużej nakładu pracy i ułatwiają zarządzanie kodem. Większość kodu specyficznego dla aplikacji znajduje się w dokumentach i widokach klas.

## <a name="see-also"></a>Zobacz też

[Używanie klas do pisania aplikacji dla systemu Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
