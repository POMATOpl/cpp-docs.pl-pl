---
description: 'Dowiedz się więcej na temat: ciągi szablonu dokumentu, Kreator aplikacji MFC'
title: Ciągi szablonu dokumentu, kreator aplikacji MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.doctemp
helpviewer_keywords:
- MFC Application Wizard, document template strings
ms.assetid: 8109f662-3182-4682-977a-2503321c678a
ms.openlocfilehash: 839626915b5e60dd47182dd42f1182a092f0b3ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219918"
---
# <a name="document-template-strings-mfc-application-wizard"></a>Ciągi szablonu dokumentu, kreator aplikacji MFC

Na tej stronie Kreatora aplikacji MFC Podaj lub Dostosuj poniższe opcje, aby pomóc w zarządzaniu dokumentami i lokalizacją. Ciągi szablonu dokumentu są dostępne dla aplikacji, które zawierają **obsługę architektury dokumentu/widoku** w [typie aplikacji](../../mfc/reference/application-type-mfc-application-wizard.md). Nie są one dostępne dla okien dialogowych. Ponieważ większość ciągów szablonów dokumentu jest widocznych i używanych przez użytkowników aplikacji, są one zlokalizowane w **języku zasobów** wskazanym na stronie **Typ aplikacji** kreatora.

- **Ciągi nielokalne**

   Dotyczy aplikacji, które tworzą dokumenty użytkownika. Użytkownicy mogą łatwiej otwierać, drukować i zapisywać dokumenty w przypadku podania rozszerzenia pliku i identyfikatora typu pliku. Te elementy nie są zlokalizowane, ponieważ są używane przez system, a nie przez użytkownika.

   |Opcja|Opis|
   |------------|-----------------|
   |**Rozszerzenie pliku**|Ustawia rozszerzenie pliku skojarzone z dokumentami zapisywanymi przez użytkownika podczas korzystania z aplikacji. Na przykład jeśli projekt nosi nazwę widget, można nazwać plik rozszerzenie. WGT. (Po wprowadzeniu rozszerzenia pliku nie należy zawierać kropki).<br /><br /> Jeśli postanowisz rozszerzenie pliku, Eksplorator może drukować dokumenty aplikacji bez uruchamiania aplikacji, gdy użytkownik porzuca ikonę dokumentu na ikonie drukarki.<br /><br /> Jeśli nie określisz rozszerzenia, użytkownik musi określić rozszerzenie pliku podczas zapisywania plików. Kreator nie udostępnia domyślnego rozszerzenia pliku.|
   |**Identyfikator typu pliku**|Ustawia etykietę dla typu dokumentu w rejestrze systemowym.|

- **Zlokalizowane ciągi**

   Tworzy ciągi skojarzone z aplikacją i dokumentem, które są odczytywane i używane przez użytkowników aplikacji, więc ciągi są zlokalizowane.

   |Opcja|Opis|
   |------------|-----------------|
   |**Język**|Wskazuje język, w którym ciągi są wyświetlane dla wszystkich pól w obszarze **zlokalizowane ciągi**. Aby zmienić wartość w tym polu, wybierz odpowiedni język w obszarze **Język zasobów** na stronie [Typ aplikacji](../../mfc/reference/application-type-mfc-application-wizard.md) w Kreatorze aplikacji MFC.|
   |**Główny podpis ramki**|Ustawia tekst wyświetlany w górnej części głównej ramki aplikacji. Domyślnie nazwa projektu.|
   |**Nazwa typu dokumentu**|Identyfikuje typ dokumentu, pod którym można grupować dokumenty aplikacji. Domyślnie nazwa projektu. Zmiana ustawienia domyślnego nie powoduje zmiany innych opcji w tym oknie dialogowym.|
   |**Nazwa filtru**|Ustawia nazwę, którą użytkownicy mogą wskazać, aby znaleźć pliki typu plików. Ta opcja jest dostępna z **plików typu** i **Zapisz jako opcje typu** w oknach dialogowych standardowych **otwartych** i **Zapisz jako** systemu Windows. Domyślnie nazwa projektu i pliki, a następnie rozszerzenie podane w **rozszerzeniu pliku**. Na przykład, jeśli projekt ma nazwę widget, a rozszerzenie pliku to. WGT, domyślnie **Nazwa filtru** to pliki widżetów (*. WGT).|
   |**Nowa krótka nazwa pliku**|Ustawia nazwę wyświetlaną w standardowym oknie **dialogowym systemu** Windows, jeśli istnieje więcej niż jeden nowy szablon dokumentu. Jeśli aplikacja jest [serwerem automatyzacji](../../mfc/automation-servers.md), ta nazwa jest używana jako krótka nazwa obiektu automatyzacji. Domyślnie nazwa projektu.|
   |**Długa nazwa typu pliku**|Ustawia nazwę typu pliku w rejestrze systemowym. Jeśli aplikacja jest serwerem automatyzacji, ta nazwa jest używana jako długa nazwa obiektu automatyzacji. Domyślnie nazwa projektu plus. Dokumentu.|

## <a name="see-also"></a>Zobacz też

[Kreator aplikacji MFC](../../mfc/reference/mfc-application-wizard.md)
