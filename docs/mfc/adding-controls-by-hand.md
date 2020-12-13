---
description: 'Dowiedz się więcej na temat: Dodawanie kontrolek według dłoni'
title: Ręczne dodawanie formantów
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
ms.openlocfilehash: f6dfa65baa037aa168697aa7abcd3eedc76cc4d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339080"
---
# <a name="adding-controls-by-hand"></a>Ręczne dodawanie formantów

Można [dodać kontrolki do okna dialogowego z edytorem okien dialogowych](using-the-dialog-editor-to-add-controls.md) lub dodać je samodzielnie, przy użyciu kodu.

Aby samodzielnie utworzyć obiekt formantu, zazwyczaj osadzisz obiekt formantu C++ w oknie dialogowym języka C++ lub w obiekcie okna ramki. Podobnie jak w przypadku wielu innych obiektów w strukturze, formanty wymagają konstrukcji dwuetapowej. Należy wywołać funkcję **tworzenia** elementu członkowskiego kontrolki w ramach tworzenia nadrzędnego okna dialogowego lub ramki. W przypadku okien dialogowych zwykle jest to wykonywane w [OnInitDialog](reference/cdialog-class.md#oninitdialog), a dla okien ramowych, w obszarze [OnCreate](reference/cwnd-class.md#oncreate).

Poniższy przykład pokazuje, jak można zadeklarować `CEdit` obiekt w deklaracji klasy pochodnej klasy dialogowej, a następnie wywołać `Create` funkcję elementu członkowskiego w `OnInitDialog` . Ponieważ `CEdit` obiekt jest zadeklarowany jako obiekt osadzony, jest automatycznie konstruowany podczas konstruowania obiektu okna dialogowego, ale nadal musi być zainicjowany przy użyciu własnej `Create` funkcji składowej.

[!code-cpp[NVC_MFCControlLadenDialog#1](codesnippet/cpp/adding-controls-by-hand_1.h)]

Poniższa `OnInitDialog` Funkcja konfiguruje prostokąt, a następnie wywołuje w `Create` celu utworzenia kontrolki edycji systemu Windows i dołączenia go do niezainicjowanego `CEdit` obiektu.

[!code-cpp[NVC_MFCControlLadenDialog#2](codesnippet/cpp/adding-controls-by-hand_2.cpp)]

Po utworzeniu obiektu edycji można także ustawić fokus wprowadzania dla kontrolki, wywołując `SetFocus` funkcję członkowską. Na koniec zwracasz wartość 0 z, `OnInitDialog` Aby pokazać, że fokus jest ustawiony. Jeśli zwracasz wartość różną od zera, Menedżer okien dialogowych ustawia fokus na pierwszy element kontrolki na liście element okna dialogowego. W większości przypadków należy dodać kontrolki do okien dialogowych za pomocą edytora okien dialogowych.

## <a name="see-also"></a>Zobacz też

[Tworzenie i używanie kontrolek](making-and-using-controls.md)<br/>
[Formanty](controls-mfc.md)<br/>
[CDialog:: OnInitDialog](reference/cdialog-class.md#oninitdialog)
