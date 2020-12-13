---
description: 'Dowiedz się więcej na temat: Przewodnik: wdrażanie aplikacji Visual C++ w folderze lokalnym aplikacji'
title: Wdrażanie aplikacji Visual C++ w folderze lokalnym aplikacji
ms.date: 04/23/2019
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
ms.openlocfilehash: c06015ea32bb9f54653e350966bd8089c98628b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135944"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>Wskazówki: wdrażanie aplikacji Visual C++ do folderu lokalnego aplikacji

Opisuje sposób wdrażania aplikacji Visual C++ przez kopiowanie plików do folderu.

## <a name="prerequisites"></a>Wymagania wstępne

- Komputer, na którym jest zainstalowany program Visual Studio.

- Inny komputer, który nie ma bibliotek Visual C++.

### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Aby wdrożyć aplikację do folderu lokalnego aplikacji

1. Utwórz i skompiluj aplikację MFC, wykonując czynności opisane w [przewodniku: wdrażanie aplikacji Visual C++ przy użyciu projektu Instalatora](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).

1. Skopiuj odpowiednie pliki biblioteki MFC i C Run-Time (CRT) z katalogu instalacyjnego programu Visual Studio w \\ \\ folderze wersji redystrybucyjnej VC \\  , a następnie wklej je w folderze \Release\ projektu MFC. Aby uzyskać więcej informacji na temat innych plików, które mogą być kopiowane, zobacz [Określanie bibliotek DLL do redystrybucji](determining-which-dlls-to-redistribute.md).

1. Uruchom aplikację MFC na drugim komputerze, który nie ma bibliotek Visual C++.

   1. Skopiuj zawartość folderu \Release\ i wklej je w folderze aplikacji na drugim komputerze.

   1. Uruchom aplikację na drugim komputerze.

   Aplikacja została uruchomiona pomyślnie, ponieważ biblioteki Visual C++ są dostępne w folderze aplikacji — lokalnym.

## <a name="see-also"></a>Zobacz też

[Przykłady wdrożeń](deployment-examples.md)<br/>
