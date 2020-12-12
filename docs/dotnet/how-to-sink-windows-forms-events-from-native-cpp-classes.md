---
description: 'Dowiedz się więcej na temat: Instrukcje: ujścia zdarzeń Windows Forms z natywnych klas C++'
title: 'Porady: wychwytywanie zdarzeń interfejsu Windows Forms z klas natywnych języka C++'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
ms.openlocfilehash: 223590849f114bfe02b030a0639f160b8fc1c321
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286361"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>Porady: wychwytywanie zdarzeń interfejsu Windows Forms z klas natywnych języka C++

Można włączyć natywne klasy języka C++, aby odbierać wywołania zwrotne z zdarzeń zarządzanych wywoływanych z formantów Windows Forms lub innych formularzy przy użyciu formatu mapy makr MFC. Zdarzenia dotyczące ujścia w widokach i oknach dialogowych przypominają wykonywanie tego samego zadania dla kontrolek.

W tym celu należy:

- Dołącz `OnClick` procedurę obsługi zdarzeń do formantu przy użyciu [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate).

- Utwórz mapę delegata przy użyciu [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)i [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry).

Ten przykład kontynuuje pracę, która została wykonana w [sposób: wykonywanie powiązania danych DDX/DDV za pomocą Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md).

Teraz zostanie skojarzona kontrolka MFC ( `m_MyControl` ) z zarządzanym delegatem obsługi zdarzeń wywołanym `OnClick` dla <xref:System.Windows.Forms.Control.Click> zdarzenia zarządzanego.

### <a name="to-attach-the-onclick-event-handler"></a>Aby dołączyć program obsługi zdarzeń onkliknięcia:

1. Dodaj następujący kod do implementacji BOOL CMFC01Dlg:: OnInitDialog:

    ```
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );
    ```

1. Dodaj następujący kod do sekcji publicznej w deklaracji klasy CMFC01Dlg: Public CDialog.

    ```
    // delegate map
    BEGIN_DELEGATE_MAP( CMFC01Dlg )
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )
    END_DELEGATE_MAP()

    void OnClick( System::Object^ sender, System::EventArgs^ e );
    ```

1. Na koniec Dodaj implementację programu `OnClick` do programu CMFC01Dlg. cpp:

    ```
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)
    {
        AfxMessageBox(_T("Button clicked"));
    }
    ```

## <a name="see-also"></a>Zobacz też

[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)<br/>
[BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)<br/>
[END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)<br/>
[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)
