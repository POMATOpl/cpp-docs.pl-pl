---
description: 'Dowiedz się więcej o: kontenery kontrolek ActiveX: Programowanie formantów ActiveX w kontenerze kontrolek ActiveX'
title: 'Kontenery formantów ActiveX: programowanie formantów ActiveX w kontenerze formantów ActiveX'
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
ms.openlocfilehash: 34a5a2aaa1d7ec940ea31ae2fbe8c89ba3d84818
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251014"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>Kontenery formantów ActiveX: programowanie formantów ActiveX w kontenerze formantów ActiveX

W tym artykule opisano proces uzyskiwania dostępu do uwidocznionych [metod](../mfc/mfc-activex-controls-methods.md) i [Właściwości](../mfc/mfc-activex-controls-properties.md) osadzonych kontrolek ActiveX.

>[!IMPORTANT]
> Kontrolka ActiveX to Starsza technologia, która nie powinna być używana do nowych celów programistycznych. Aby uzyskać więcej informacji na temat nowoczesnych technologii, które zastępują ActiveX, zobacz [kontrolki ActiveX](activex-controls.md).

W zasadzie należy wykonać następujące czynności:

1. [Wstaw kontrolkę ActiveX do projektu kontenera ActiveX](../mfc/inserting-a-control-into-a-control-container-application.md) przy użyciu galerii.

1. [Zdefiniuj zmienną członkowską](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (lub inną formę dostępu) tego samego typu co Klasa otoki kontrolki ActiveX.

1. [Program kontrolki ActiveX](#_core_programming_the_activex_control) przy użyciu wstępnie zdefiniowanych funkcji członkowskich klasy otoki.

W przypadku tej dyskusji Załóżmy, że utworzono projekt oparty na oknach dialogowych (nazwany kontener) z obsługą formantów ActiveX. Przykładowa kontrolka "okólnik" zostanie dodana do projektu będącego wynikiem.

Gdy formant cykl zostanie wstawiony do projektu (krok 1), Wstaw wystąpienie kontrolki cykl w głównym oknie dialogowym aplikacji.

## <a name="procedures"></a>Procedury

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Aby dodać formant cykl do szablonu okna dialogowego

1. Załaduj projekt kontenera kontrolki ActiveX. Na potrzeby tego przykładu Użyj `Container` projektu.

1. Kliknij kartę Widok zasobów.

1. Otwórz folder **okna dialogowego** .

1. Kliknij dwukrotnie główny szablon okna dialogowego. Na potrzeby tego przykładu Użyj **IDD_CONTAINER_DIALOG**.

1. Kliknij ikonę "cykl" w przyborniku.

1. Kliknij punkt w oknie dialogowym, aby wstawić formant cykl.

1. Z menu **plik** wybierz polecenie **Zapisz wszystko** , aby zapisać wszystkie modyfikacje w szablonie okna dialogowego.

## <a name="modifications-to-the-project"></a>Modyfikacje projektu

Aby umożliwić aplikacji kontenera dostęp do kontrolki cykl, Visual C++ automatycznie dodaje plik implementacji klasy otoki ( `CCirc` ) (. CPP) do projektu kontenera i nagłówka klasy otoki (. H) plik do pliku nagłówkowego okna dialogowego:

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

## <a name="the-wrapper-class-header-h-file"></a><a name="_core_the_wrapper_class_header_28h29_file"></a> Nagłówek klasy otoki (. H) plik

Aby uzyskać i ustawić właściwości (i wywołać metody) dla kontrolki cykl, `CCirc` Klasa otoki zawiera deklarację wszystkich uwidocznionych metod i właściwości. W tym przykładzie te deklaracje znajdują się w CYKLach. H. Poniższy przykład jest częścią klasy `CCirc` , która definiuje uwidocznione interfejsy kontrolki ActiveX:

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

Te funkcje można następnie wywołać z innych procedur aplikacji przy użyciu standardowej składni języka C++. Aby uzyskać więcej informacji na temat używania tej funkcji elementu członkowskiego do uzyskiwania dostępu do metod i właściwości kontrolki, zobacz sekcję [programowanie kontrolki ActiveX](#_core_programming_the_activex_control).

## <a name="member-variable-modifications-to-the-project"></a><a name="_core_member_variable_modifications_to_the_project"></a> Modyfikowanie zmiennej składowej do projektu

Po dodaniu kontrolki ActiveX do projektu i osadzonym w kontenerze okna dialogowego dostęp do niego mogą uzyskać inne części projektu. Najprostszym sposobem uzyskania dostępu do formantu jest [utworzenie zmiennej składowej](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) klasy okna dialogowego `CContainerDlg` (krok 2), która jest tego samego typu co Klasa otoki dodana do projektu przez Visual C++. Następnie można użyć zmiennej składowej w celu uzyskania dostępu do osadzonego formantu w dowolnym momencie.

Gdy okno dialogowe **Dodawanie zmiennej składowej** dodaje do projektu zmienną członkowską *m_circctl* , dodaje również następujące wiersze do pliku nagłówkowego (. H) `CContainerDlg` klasy:

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

Ponadto wywołanie **DDX_Control** jest automatycznie dodawane do `CContainerDlg` implementacji `DoDataExchange` :

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

## <a name="programming-the-activex-control"></a><a name="_core_programming_the_activex_control"></a> Programowanie kontrolki ActiveX

W tym momencie wstawiono kontrolkę ActiveX do szablonu okna dialogowego i utworzono dla niej zmienną członkowską. Teraz można użyć typowej składni języka C++, aby uzyskać dostęp do właściwości i metod osadzonego formantu.

Jak wskazano (w [nagłówku klasy otoki (. H)](#_core_the_wrapper_class_header_28h29_file)plik nagłówka (. H) dla `CCirc` klasy otoki, w tym przypadku cykl. H, zawiera listę funkcji Członkowskich, których można użyć do pobierania i ustawiania wartości właściwości uwidocznionej. Dostępne są również funkcje członkowskie dla uwidocznionych metod.

Typowym miejscem modyfikacji właściwości kontrolki jest `OnInitDialog` funkcja członkowska klasy głównego okna dialogowego. Ta funkcja jest wywoływana tuż przed wyświetleniem okna dialogowego i służy do zainicjowania jego zawartości, w tym wszystkich kontrolek.

Poniższy przykład kodu używa zmiennej składowej *m_circctl* , aby zmodyfikować podpis i właściwości CircleShape osadzonej kontrolki cykl:

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>Zobacz też

[Kontenery kontrolek ActiveX](../mfc/activex-control-containers.md)
