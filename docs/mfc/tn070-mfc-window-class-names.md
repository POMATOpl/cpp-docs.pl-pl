---
description: 'Dowiedz się więcej o: TN070: nazwy klas okien MFC'
title: 'TN070: nazwy klas okien MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: 963f343f480a5805a3c1ec3cf5499583a17535ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214523"
---
# <a name="tn070-mfc-window-class-names"></a>TN070: nazwy klas okien MFC

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Windows MFC używa dynamicznie utworzonej nazwy klasy, która odzwierciedla funkcje okna. MFC generuje nazwy klas dynamicznie dla okien ramowych, widoków i okien podręcznych tworzonych przez aplikację. Okna dialogowe i kontrolki tworzone przez aplikację MFC mają nazwę dostarczoną przez system Windows dla danej klasy okna.

Można zastąpić dynamiczną nazwę klasy przez zarejestrowanie własnej klasy okna i użycie jej w przesłonięciu [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow). Nazwy klas dostarczone przez MFC pasują do jednej z dwóch następujących form:

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

Cyfry szesnastkowe, które zastępują `%x` znaki, są wypełniane danymi ze struktury [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) . MFC korzysta z tej techniki, dzięki czemu wiele klas C++ wymagających identycznych struktur **WNDCLASS** może współużytkować tę samą zarejestrowanej klasy okna. W przeciwieństwie do większości prostych aplikacji Win32, aplikacje MFC mają tylko jeden **WndProc**, więc można łatwo udostępniać struktury **WNDCLASS** , aby zaoszczędzić czas i pamięć. Wartości do przemieszczenia dla `%x` przedstawionych powyżej znaków są następujące:

- **WNDCLASS. hInstance**

- **WNDCLASS. Style**

- **WNDCLASS.hCursor**

- **WNDCLASS.hbrBackground**

- **WNDCLASS.hIcon**

Pierwszy formularz ( `Afx:%x:%x` ) jest używany, gdy **hCursor**, **HbrBackground** i **HICON** mają **wartość null**.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)<br/>
[TN020: Konwencje nazewnictwa i numerowania identyfikatorów](../mfc/tn020-id-naming-and-numbering-conventions.md)
