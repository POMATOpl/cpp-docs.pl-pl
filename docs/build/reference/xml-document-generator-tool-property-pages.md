---
description: 'Dowiedz się więcej o: strony właściwości narzędzia generatora dokumentów XML'
title: Strony właściwości narzędzia generowania dokumentów XML
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
ms.openlocfilehash: e344d8ef796a5c3455c88851a1fc410801b991bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260972"
---
# <a name="xml-document-generator-tool-property-pages"></a>Strony właściwości narzędzia generowania dokumentów XML

Strona właściwości narzędzia generatora dokumentów XML udostępnia funkcje xdcmake.exe. xdcmake.exe scala pliki. xdc w pliku XML, gdy kod źródłowy zawiera komentarze do dokumentacji i [/doc (Przetwarzaj komentarze dokumentacji) (C/C++)](doc-process-documentation-comments-c-cpp.md) jest określony,. Aby uzyskać informacje na temat dodawania komentarzy do dokumentacji do kodu źródłowego, zobacz [zalecane Tagi komentarzy dokumentacji](recommended-tags-for-documentation-comments-visual-cpp.md) .

> [!NOTE]
> Opcje xdcmake.exe w środowisku programistycznym (strony właściwości) różnią się w zależności od opcji, gdy xdcmake.exe jest używana w wierszu polecenia. Aby uzyskać informacje na temat używania xdcmake.exe w wierszu polecenia, zobacz [xdcmake Reference](xdcmake-reference.md).

## <a name="uielement-list"></a>Lista elementów UI

- **Pomiń transparent startowy**

   Pomiń komunikat o prawach autorskich.

- **Dodatkowe pliki dokumentów**

   Dodatkowe katalogi, w których system projektu ma szukać plików XDC. xdcmake będzie zawsze szukać plików. xdc generowanych przez projekt. Można określić wiele katalogów.

- **Plik dokumentu wyjściowego**

   Nazwa i lokalizacja katalogu wyjściowego pliku. XML. Aby określić lokalizacje katalogów [, zobacz Typowe makra dotyczące poleceń i właściwości kompilacji](common-macros-for-build-commands-and-properties.md) .

- **Zależności biblioteki dokumentów**

   Jeśli projekt ma zależność od projektu. lib w rozwiązaniu, można przetwarzać pliki. xdc z projektu. lib do plików. XML dla bieżącego projektu.

## <a name="see-also"></a>Zobacz też

[Odwołanie do strony właściwości projektu C++](property-pages-visual-cpp.md)
