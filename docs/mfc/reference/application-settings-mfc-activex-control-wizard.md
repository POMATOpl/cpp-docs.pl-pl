---
description: 'Dowiedz się więcej na temat: ustawienia aplikacji, Kreator kontrolek ActiveX MFC'
title: Ustawienia aplikacji, kreator kontrolek ActiveX MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.appset
helpviewer_keywords:
- MFC ActiveX Control Wizard, application settings
ms.assetid: 48475194-cc63-467f-8499-f142269a4c1c
ms.openlocfilehash: dac370f7ba3461534f2fd4782869e7ddcb50336a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322814"
---
# <a name="application-settings-mfc-activex-control-wizard"></a>Ustawienia aplikacji, kreator kontrolek ActiveX MFC

Użyj tej strony kreatora kontrolek ActiveX MFC, aby zaprojektować i dodać podstawowe funkcje do nowego projektu MFC ActiveX. Te ustawienia mają zastosowanie do samej aplikacji, a nie do żadnej konkretnej funkcji lub elementu formantu.

- **Licencja czasu wykonywania**

   Wybierz tę opcję, aby wygenerować plik licencji użytkownika na potrzeby dystrybucji z kontrolką. Licencja to plik tekstowy, *Projname*. lic. Ten plik musi znajdować się w tym samym katalogu co Biblioteka DLL kontrolki, aby zezwalać na tworzenie wystąpienia formantu w środowisku czasu projektowania. Zazwyczaj ten plik jest dystrybuowany z kontrolką, ale nie są one dystrybuowane przez klientów.

- **Generuj pliki pomocy**

   Wybierz tę opcję, aby wygenerować pliki pomocy użyto metod zastępczych i skonfigurować projekt w celu dołączenia pomocy do kontrolki. Projekt domyślny utworzony bez tej opcji generuje tylko pole **informacje** , które jest wyświetlane, gdy użytkownik kliknie prawym przyciskiem myszy, użyje klawisza F1 lub kliknie w kontenerze kontrolki **Pomoc** .

   > [!NOTE]
   > Sposób wyświetlania pomocy zależy od tego, w jaki sposób formant współdziała z jego kontenerem. Jeśli dołączysz pomoc do swojego kontenera, musisz obsługiwać komunikaty między formantem i kontenerem, aby wyświetlić pomoc odpowiednio.

   W przypadku generowania plików pomocy przy użyciu kreatora Projekt zawiera następujące elementy:

  - Plik. vcxproj zawiera kod do kompilowania i konfigurowania pliku pomocy po skompilowaniu projektu.

  - Plik *projnamePropPage*. cpp zawiera funkcję [SetHelpInfo](../../mfc/reference/colepropertypage-class.md#sethelpinfo) w konstruktorze.

  - Plik PROJ. hpj jest plikiem projektu pomocy używanym przez kompilator pomocy do tworzenia pliku pomocy kontrolki ActiveX. Plik. hpj to plik tekstowy zawierający informacje o kompilowaniu pliku pomocy oraz ścieżki do dodatkowych plików (na przykład mapy bitowe), które zawiera plik pomocy.

  - Projekt zawiera katalog HLP zawierający pliki map bitowych pomocy projektu i plik tematu pomocy (*Projname*. rtf). Ten plik tematu pomocy zawiera standardowe tematy pomocy dotyczące typowych właściwości, zdarzeń i metod obsługiwanych przez wiele formantów ActiveX. Plik. rtf można edytować w celu dodania lub usunięcia określonych tematów pomocy.

## <a name="see-also"></a>Zobacz też

[Kreator kontrolek ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Nazwy kontrolek, Kreator kontrolek ActiveX MFC](../../mfc/reference/control-names-mfc-activex-control-wizard.md)<br/>
[Ustawienia kontrolki, Kreator kontrolek ActiveX MFC](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)
