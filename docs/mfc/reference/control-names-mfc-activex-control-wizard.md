---
description: 'Dowiedz się więcej na temat: nazwy kontrolek, Kreator kontrolek ActiveX MFC'
title: Nazwy kontrolek, kreator kontrolek ActiveX MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.names
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
ms.openlocfilehash: 26d329465c13c3988a3e9d4d7ccd06294f3b2be3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345241"
---
# <a name="control-names-mfc-activex-control-wizard"></a>Nazwy kontrolek, kreator kontrolek ActiveX MFC

Określ nazwy klasy kontrolki i klasy strony właściwości, nazwy typów i identyfikatory typów dla kontrolki. Z wyjątkiem **krótkiej nazwy** wszystkie inne pola można edytować niezależnie. Jeśli zmienisz tekst **skróconej nazwy**, zmiana zostanie odzwierciedlona w nazwach wszystkich innych pól na tej stronie. Takie zachowanie nazewnictwa zostało zaprojektowane, aby wszystkie nazwy były łatwo rozpoznawalne podczas tworzenia kontrolki.

- **Krótka nazwa**

   Podaj skróconą nazwę formantu. Domyślnie ta nazwa jest oparta na nazwie projektu podanej w oknie dialogowym **Nowy projekt** . Wprowadzona nazwa określa nazwy klas, nazwy typów i identyfikatory typów, chyba że te pola są zmieniane pojedynczo.

- **Nazwa klasy kontrolki**

   Domyślnie nazwa klasy kontrolki jest oparta na krótkiej nazwie, z `C` prefiksem i `Ctrl` jako sufiksem. Na przykład, jeśli krótka nazwa kontrolki to `Price` , nazwa klasy kontrolki to `CPriceCtrl` .

- **Plik Control. h**

   Domyślnie nazwa pliku nagłówka jest określana na podstawie krótkiej nazwy, za pomocą `Ctrl` sufiksu i `.h` jako rozszerzenia pliku. Na przykład, jeśli krótka nazwa kontrolki to `Price` , nazwa pliku nagłówka to `PriceCtrl.h` . Nazwa w tym polu powinna być zgodna z nazwą klasy formantu.

- **Plik CPP kontrolki**

   Domyślnie nazwa pliku nagłówka jest określana na podstawie krótkiej nazwy, za pomocą `Ctrl` sufiksu i `.cpp` jako rozszerzenia pliku. Na przykład, jeśli krótka nazwa kontrolki to `Price` , nazwa pliku nagłówka to `PriceCtrl.cpp` . Nazwa w tym polu powinna być zgodna z nazwą nagłówka.

- **Nazwa typu formantu**

   Domyślnie nazwa typu formantu jest oparta na krótkiej nazwie, a następnie `Control` . Na przykład, jeśli krótka nazwa kontrolki to `Price` , nazwa typu klasy kontrolki to `Price Control` . Jeśli zmienisz wartość w tym polu, upewnij się, że nazwa wskazuje dziedziczenie.

- **Identyfikator typu formantu**

   Ustawia identyfikator typu kontrolki klasy formantu. Formant zapisuje ten ciąg w rejestrze, gdy zostanie on dodany do projektu. Aplikacje kontenera używają tego ciągu do tworzenia wystąpienia formantu.

   Domyślnie identyfikator typu formantu jest określany na podstawie nazwy projektu, który został wskazany w oknie dialogowym **Nowy projekt** i krótka nazwa. Ta nazwa powinna być zgodna z nazwą typu.

   Domyślnie identyfikator typu formantu jest wyświetlany w następujący sposób:

   *ProjectName. ShortName* Ctrl. 1

   Jeśli zmienisz krótką nazwę w tym oknie dialogowym, identyfikator typu formantu zostanie wyświetlony w następujący sposób:

   *ProjectName. NewShortName* Ctrl. 1

- **Nazwa klasy PropPage**

   Domyślnie nazwa klasy strony właściwości jest oparta na krótkiej nazwie, z `C` prefiksem i `PropPage` jako sufiksem. Na przykład, jeśli krótka nazwa kontrolki to `Price` , nazwa klasy strony właściwości to `CPricePropPage` . Ta nazwa powinna być zgodna z nazwą klasy formantu, dołączoną z `PropPage` .

- **Plik PropPage. h**

   Domyślnie nazwa pliku nagłówka strony właściwości jest określana na podstawie krótkiej nazwy, jako `PropPage` sufiksu i jako `.h` rozszerzenia pliku. Na przykład, jeśli krótka nazwa kontrolki to `Price` , nazwa pliku nagłówka strony właściwości to `PricePropPage.h` . Ta nazwa powinna być zgodna z nazwą klasy.

- **Plik PropPage. cpp**

   Domyślnie nazwa pliku implementacji strony właściwości jest określana na podstawie krótkiej nazwy, jako `PropPage` sufiksu i jako `.cpp` rozszerzenia pliku. Na przykład, jeśli krótka nazwa kontrolki to `Price` , nazwa pliku nagłówka strony właściwości to `PricePropPage.cpp` . Ta nazwa powinna być zgodna z nazwą pliku nagłówkowego.

- **Nazwa typu PropPage**

   Domyślnie nazwa typu strony właściwości jest określana na podstawie krótkiej nazwy, a następnie `Property Page` . Na przykład, jeśli krótka nazwa kontrolki to `Price` , nazwa typu strony właściwości to `Price Property Page` . Jeśli zmienisz wartość w tym polu, upewnij się, że nazwa wskazuje klasę kontrolki.

- **Identyfikator typu PropPage**

   Ustawia identyfikator klasy strony właściwości. Formant zapisuje ten ciąg w rejestrze, gdy zostanie on zastosowany do projektu. Aplikacja kontenera używa tego ciągu do utworzenia wystąpienia strony właściwości kontrolki.

   Domyślnie identyfikator typu strony właściwości jest oparty na nazwie projektu, który został wskazany w oknie dialogowym **Nowy projekt** i krótka nazwa. Ta nazwa powinna być zgodna z nazwą typu.

   Domyślnie identyfikator typu strony właściwości jest wyświetlany w następujący sposób:

   *ProjectName. ShortName* PropPage. 1

   Jeśli zmienisz krótką nazwę w tym oknie dialogowym, identyfikator typu strony właściwości będzie wyświetlany w następujący sposób:

   *ProjectName. NewShortName* PropPage. 1

## <a name="see-also"></a>Zobacz też

[Kreator kontrolek ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Ustawienia aplikacji, Kreator kontrolek ActiveX MFC](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[Ustawienia kontrolki, Kreator kontrolek ActiveX MFC](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)<br/>
[Typy plików utworzone dla projektów Visual Studio C++](../../build/reference/file-types-created-for-visual-cpp-projects.md)
