---
description: 'Dowiedz się więcej na temat: Tworzenie kontenera kontrolek ActiveX MFC'
title: Tworzenie kontenera kontrolek ActiveX MFC
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.activex.container
helpviewer_keywords:
- MFC ActiveX controls [MFC], containers
- ActiveX control containers [MFC], creating
- containers [MFC], creating
- OLE controls [MFC], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
ms.openlocfilehash: 221edf8cfaefb55b919c1117becc074cdfd880ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343195"
---
# <a name="creating-an-mfc-activex-control-container"></a>Tworzenie kontenera kontrolek ActiveX MFC

Kontener formantów ActiveX jest programem nadrzędnym, który dostarcza środowisko do uruchamiania kontrolki ActiveX (dawniej OLE). Można utworzyć aplikację, która może zawierać kontrolki ActiveX z MFC lub bez, ale jest to znacznie łatwiejsze w przypadku MFC.

>[!IMPORTANT]
> Kontrolka ActiveX to Starsza technologia, która nie powinna być używana do nowych celów programistycznych. Aby uzyskać więcej informacji na temat nowoczesnych technologii, które zastępują ActiveX, zobacz [kontrolki ActiveX](../activex-controls.md).

Tworzenie programu kontenera MFC przy użyciu [Kreatora aplikacji MFC](../../mfc/reference/mfc-application-wizard.md) pozwala uzyskać dostęp do wielu funkcji formantów ActiveX i automatyzacji, które są implementowane przez klasy MFC i ActiveX. Te funkcje obejmują edycję wizualizacji, automatyzację, tworzenie plików złożonych i obsługę formantów. Opcje edycji wizualnej Kreatora aplikacji MFC, które będą obsługiwane przez program nadrzędny, obejmują tworzenie kontenera, mini serwer, pełny serwer i program, który jest zarówno kontenerem, jak i serwerem.

- **Nowa aplikacja MFC**. Aby utworzyć nowy program MFC, który obejmuje automatyzację, edycję wizualizacji, pliki złożone lub obsługę kontroli, użyj Kreatora aplikacji MFC i wybierz odpowiednie opcje automatyzacji.

- **Istniejąca aplikacja MFC**. Jeśli dodajesz kontrolkę zawieranie do istniejącej aplikacji MFC, zobacz [kontenery kontrolek OLE: ręczne włączanie zawierania kontrolek OLE](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).

### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>Aby utworzyć kontener ActiveX dla dowolnego z następujących typów aplikacji

1. [Containers](../../mfc/containers.md)

1. [Edytowanie wizualizacji](../../mfc/ole-mfc.md)

1. [kontrolki ActiveX MFC](../../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>Zobacz też

[Typy projektów C++ w programie Visual Studio](../../build/reference/visual-cpp-project-types.md)
