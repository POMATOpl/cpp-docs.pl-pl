---
description: 'Dowiedz się więcej na temat: jak kompilować Registration-Free składniki COM'
title: 'Porady: kompilowanie komponentów COM bez rejestrowania'
ms.date: 11/04/2016
helpviewer_keywords:
- COM components, registration-free
ms.assetid: 7e585d6a-0314-45b2-8f1b-cae9ac4df037
ms.openlocfilehash: ddcb378989878749d170705b4808d8302523a73a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162719"
---
# <a name="how-to-build-registration-free-com-components"></a>Porady: kompilowanie komponentów COM bez rejestrowania

Składniki COM bez rejestracji to składniki COM, które mają wbudowane manifesty w bibliotekach DLL.

### <a name="to-build-manifests-into-com-components"></a>Aby skompilować manifesty do składników COM

1. Otwórz strony właściwości projektu dla składnika COM.

1. Rozwiń węzeł **Właściwości konfiguracji** , a następnie rozwiń węzeł **narzędzie manifestu** .

1. Wybierz stronę właściwości **dane wejściowe i wyjściowe** , a następnie ustaw właściwość **Osadź manifest** równą **tak**.

1. Kliknij przycisk **OK**.

1. Skompiluj rozwiązanie.

## <a name="see-also"></a>Zobacz też

[Instrukcje: Kompilowanie izolowanych aplikacji do korzystania ze składników COM](how-to-build-isolated-applications-to-consume-com-components.md)
