---
description: Dowiedz się więcej na temat operacji przeciągania i upuszczania kontrolki drzewa
title: Operacje przeciągania i upuszczania formantu drzewa
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
ms.openlocfilehash: 000255ad4aa6801cbe27676603a3f42d0abbef30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264183"
---
# <a name="tree-control-drag-and-drop-operations"></a>Operacje przeciągania i upuszczania formantu drzewa

Kontrolka drzewa ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) wysyła powiadomienie, gdy użytkownik rozpocznie przeciąganie elementu. Kontrolka wysyła [TVN_BEGINDRAG](/windows/win32/Controls/tvn-begindrag) komunikat powiadomienia, gdy użytkownik rozpocznie przeciąganie elementu z lewym przyciskiem myszy i [TVN_BEGINRDRAG](/windows/win32/Controls/tvn-beginrdrag) komunikatem powiadomienia, gdy użytkownik rozpocznie przeciąganie za pomocą przycisku po prawej stronie. Można zapobiec wysyłaniu przez formant drzewa tych powiadomień, poprzez nadanie formantowi drzewa TVS_DISABLEDRAGDROP stylu.

Uzyskanie obrazu do wyświetlenia podczas operacji przeciągania przez wywołanie funkcji składowej [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) . Formant drzewa tworzy mapę bitową w oparciu o etykietę przeciąganego elementu. Następnie formant drzewa tworzy listę obrazów, dodaje do niej mapę bitową i zwraca wskaźnik do obiektu [Korzystanie CImageList](../mfc/reference/cimagelist-class.md) .

Należy podać kod, który faktycznie przeciąga element. Zwykle polega to na użyciu możliwości przeciągania funkcji list obrazów i przetwarzania komunikatów [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) i [WM_LBUTTONUP](/windows/win32/inputdev/wm-lbuttonup) (lub [WM_RBUTTONUP](/windows/win32/inputdev/wm-rbuttonup)) wysyłanych po rozpoczęciu operacji przeciągania. Aby uzyskać więcej informacji na temat funkcji list obrazu, zobacz [Korzystanie CImageList](../mfc/reference/cimagelist-class.md) in the *MFC References* and [image lists](/windows/win32/controls/image-lists) in the Windows SDK. Aby uzyskać więcej informacji na temat przeciągania elementu kontrolki drzewa, zobacz [przeciąganie elementu widoku drzewa](/windows/win32/Controls/tree-view-controls), również w Windows SDK.

Jeśli elementy w formancie drzewa mają być obiektami docelowymi operacji przeciągania i upuszczania, musisz wiedzieć, kiedy wskaźnik myszy znajduje się na elemencie docelowym. Możesz sprawdzić, wywołując funkcję elementu członkowskiego [HitTest](../mfc/reference/ctreectrl-class.md#hittest) . Należy określić punkt i liczbę całkowitą albo adres struktury [TVHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-tvhittestinfo) , która zawiera bieżące współrzędne kursora myszy. Gdy funkcja zwraca, liczba całkowita lub struktura zawiera flagę wskazującą lokalizację kursora myszy względem kontrolki drzewa. Jeśli kursor znajduje się nad elementem w kontrolce drzewa, struktura zawiera również uchwyt elementu.

Można wskazać, że element jest obiektem docelowym operacji przeciągania i upuszczania przez wywołanie funkcji elementu członkowskiego [SetItem](../mfc/reference/ctreectrl-class.md#setitem) , aby ustawić stan na `TVIS_DROPHILITED` wartość. Element, który ma ten stan, jest rysowany w stylu używanym do wskazywania docelowego przeciągania i upuszczania.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)
