---
description: 'Dowiedz się więcej na temat: standardowe identyfikatory poleceń i okien'
title: Identyfikatory poleceń standardowych i okien
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: 9f5a6b59d9451d749a48443bddf3560d2702bfe5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218904"
---
# <a name="standard-command-and-window-ids"></a>Identyfikatory poleceń standardowych i okien

Biblioteka MFC definiuje szereg standardowych identyfikatorów poleceń i okien w plik AFXRES. h. Te identyfikatory są najczęściej używane w ramach edytorów zasobów i [kreatora klas](mfc-class-wizard.md) do mapowania komunikatów do funkcji programu obsługi. Wszystkie polecenia standardowe mają prefiks **ID_** . Na przykład, jeśli używasz edytora menu, zwykle utworzysz element menu Otwórz plik do standardowego identyfikatora polecenia ID_FILE_OPEN.

W przypadku większości poleceń standardowych kod aplikacji nie musi odwoływać się do identyfikatora polecenia, ponieważ sama struktura obsługuje polecenia za pomocą map komunikatów w podstawowych klasach struktury (,,,, itd `CWinThread` `CWinApp` `CView` `CDocument` .).

Oprócz standardowych identyfikatorów poleceń zdefiniowane są różne identyfikatory standardowe, które mają prefiks **AFX_ID**. Identyfikatory obejmują standardowe identyfikatory okna (prefiks      **AFX_IDW_**), identyfikatory ciągów ( **AFX_IDS_** prefiks) i kilka innych typów.

Identyfikatory zaczynające się od prefiksu **AFX_ID** są rzadko używane przez programistów, ale może być konieczne odwoływanie się do tych identyfikatorów podczas zastępowania funkcji platformy, które również odnoszą się do **AFX_ID** s.

Identyfikatory nie są indywidualnie udokumentowane w tym odwołaniu. Więcej informacji na ten temat można znaleźć w uwagach technicznych [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md)i [22](../../mfc/tn022-standard-commands-implementation.md).

> [!NOTE]
> Plik nagłówkowy plik AFXRES. h jest pośrednio zawarty w afxwin. h. W pliku skryptu zasobu (. RC) aplikacji należy jawnie uwzględnić następujące instrukcje:

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>Zobacz też

[Makra i Globals](../../mfc/reference/mfc-macros-and-globals.md)
