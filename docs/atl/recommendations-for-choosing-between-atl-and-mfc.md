---
description: 'Dowiedz się więcej o: zalecenia dotyczące wybierania między ATL i MFC'
title: Zalecenia dotyczące wybierania między ATL i MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: 506df04ebbd3bc9079e1d40cf14773d9d9a6bd1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159157"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>Zalecenia dotyczące wybierania między ATL i MFC

Podczas tworzenia składników i aplikacji można wybrać dwa podejścia — ATL i MFC (biblioteka MFC).

## <a name="using-atl"></a>Przy użyciu ATL

ATL to szybki i łatwy sposób tworzenia składnika modelu COM w języku C++ i utrzymania małego rozmiaru. Użyj ATL, aby utworzyć kontrolkę, jeśli nie są potrzebne wszystkie wbudowane funkcje zapewniane przez MFC.

## <a name="using-mfc"></a>Korzystanie z MFC

MFC umożliwia tworzenie pełnych aplikacji, kontrolek ActiveX i dokumentów aktywnych. Jeśli utworzono już formant z MFC, możesz kontynuować programowanie w MFC. Podczas tworzenia nowej kontrolki należy rozważyć użycie ATL, jeśli nie są potrzebne wszystkie wbudowane funkcje MFC.

## <a name="using-atl-in-an-mfc-project"></a>Używanie ATL w projekcie MFC

Można dodać obsługę używania ATL w istniejącym projekcie MFC przez uruchomienie kreatora. Aby uzyskać szczegółowe informacje, zobacz [Dodawanie obsługi ATL do projektu MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

## <a name="see-also"></a>Zobacz też

[Wprowadzenie do ATL](../atl/introduction-to-atl.md)
