---
description: 'Dowiedz się więcej o: wywoływaniu kodu C++ z DHTML'
title: Wywoływanie kodu C++ z DHTML
ms.date: 11/04/2016
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
ms.openlocfilehash: d880b0e9cb2f0b9d5228df7da4fc96fceeb87943
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148489"
---
# <a name="calling-c-code-from-dhtml"></a>Wywoływanie kodu C++ z DHTML

Kontrolka DHTML może być hostowana w kontenerze, takim jak kontener testowy lub program Internet Explorer. Zobacz [testowanie właściwości i zdarzeń za pomocą kontenera testów,](../mfc/testing-properties-and-events-with-test-container.md) Aby uzyskać informacje na temat uzyskiwania dostępu do kontenera testowego.

Kontener obsługujący formant komunikuje się z kontrolką przy użyciu interfejsów kontroli normalnego. W języku DHTML jest używany interfejs wysyłania kończący się ciągiem "UI", aby komunikować się z kodem C++ i zasobem HTML. W przypadku [modyfikowania kontrolki DHTML ATL](../atl/modifying-the-atl-dhtml-control.md)można w ten sposób dodać metody, które mają być wywoływane przez te różne interfejsy.

Aby zobaczyć przykład wywołania kodu C++ z DHTML, [Utwórz kontrolkę DHTML](../atl/creating-an-atl-dhtml-control.md) przy użyciu kreatora kontrolki ATL i sprawdź kod w pliku nagłówkowym i pliku HTML.

## <a name="declaring-webbrowser-methods-in-the-header-file"></a>Deklarowanie metod WebBrowser w pliku nagłówkowym

Aby wywołać metody języka C++ z interfejsu użytkownika DHTML, należy dodać metody do interfejsu interfejsu użytkownika kontrolki. Na przykład plik nagłówka utworzony przez kreatora kontrolki ATL zawiera metodę języka C++ `OnClick` , która jest elementem członkowskim interfejsu interfejsu użytkownika kontrolki generowanej przez kreatora.

Sprawdź `OnClick` plik. h formantu:

[!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]

Pierwszy parametr, *pdispBody*, jest wskaźnikiem do interfejsu wysyłania obiektu treści. Drugi parametr, *varColor*, określa kolor, który ma zostać zastosowany do kontrolki.

## <a name="calling-c-code-in-the-html-file"></a>Wywoływanie kodu C++ w pliku HTML

Po zadeklarowaniu metod WebBrowser w pliku nagłówkowym można wywołać metody z pliku HTML. Zwróć uwagę na plik HTML, który Kreator kontrolki ATL wstawia trzy metody wysyłania systemu Windows: trzy `OnClick` metody, które wysyłają komunikaty, aby zmienić kolor tła kontrolki.

Zapoznaj się z jedną z metod w pliku HTML:

`<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`

W powyższym kodzie HTML Metoda zewnętrzna Window, `OnClick` , jest wywoływana jako część taga Button. Metoda ma dwa parametry: `theBody` , który odwołuje się do treści dokumentu HTML i `"red"` , co oznacza, że kolor tła kontrolki zostanie zmieniony na czerwony, gdy przycisk zostanie kliknięty. `Red`Następujący tag jest etykietą przycisku.

Aby uzyskać więcej informacji o udostępnianiu własnych metod [, zobacz Modyfikowanie kontrolki DHTML ATL](../atl/modifying-the-atl-dhtml-control.md) . Zobacz [Identyfikowanie elementów projektu kontrolki DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) , aby uzyskać więcej informacji na temat pliku HTML.

## <a name="see-also"></a>Zobacz też

[Obsługa formantów DHTML](../atl/atl-support-for-dhtml-controls.md)
