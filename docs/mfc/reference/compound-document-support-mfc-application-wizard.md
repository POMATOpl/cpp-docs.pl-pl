---
description: 'Dowiedz się więcej na temat: Obsługa dokumentu złożonego, Kreator aplikacji MFC'
title: Obsługa dokumentów złożonych, kreator aplikacji MFC
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.compdoc
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
ms.openlocfilehash: 5ccd95812c7b8a4379528b4c784a3d7ca09f538f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331364"
---
# <a name="compound-document-support-mfc-application-wizard"></a>Obsługa dokumentów złożonych, kreator aplikacji MFC

Na tej stronie Kreatora aplikacji MFC wskaż, jaki poziom aplikacji zapewnia wsparcie złożone i dokumenty aktywne. Aplikacja musi obsługiwać architekturę dokumentu/widoku do obsługi dokumentów złożonych i szablonów dokumentów.

Domyślnie aplikacja nie zawiera obsługi dokumentu złożonego. W przypadku zaakceptowania tego ustawienia domyślnego aplikacja nie może obsługiwać dokumentów aktywnych ani plików złożonych.

- **Obsługa dokumentu złożonego**

  Określa, czy aplikacja zapewnia obsługę kontenerów, obsługę serwera lub oba te elementy. Aby uzyskać więcej informacji na temat tego obszaru, zobacz:

  - [Kontenery: implementowanie kontenera](../../mfc/containers-implementing-a-container.md)

  - [Serwery: implementowanie serwera](../../mfc/servers-implementing-a-server.md)

  |Opcja|Opis|
  |------------|-----------------|
  |**Brak**|Wskazuje brak obsługi łączenia i osadzania obiektów (OLE). Domyślnie Kreator aplikacji tworzy aplikację bez obsługi ActiveX.|
  |**Kontener**|Zawiera połączone i osadzone obiekty.|
  |**Serwer mini**|Wskazuje, że aplikacja może tworzyć obiekty dokumentu złożonego i zarządzać nimi. Należy zauważyć, że serwery mini nie mogą działać autonomicznie i obsługują tylko elementy osadzone.|
  |**Pełny serwer**|Wskazuje, że aplikacja może tworzyć obiekty dokumentu złożonego i zarządzać nimi. Pełne serwery mogą uruchamiać się autonomicznie i obsługiwać zarówno elementy połączone, jak i osadzone.|
  |**Kontener/pełny serwer**|Wskazuje, że aplikacja może być zarówno kontenerem, jak i serwerem. Kontener to aplikacja, która może zawierać osadzone lub połączone elementy w swoich własnych dokumentach. Serwer to aplikacja, która może tworzyć elementy automatyzacji do użycia przez aplikacje kontenerów.|

- **Opcje dodatkowe**

  Wskazuje, czy aplikacja obsługuje dokumenty aktywne. Aby uzyskać więcej informacji na temat tej funkcji, zobacz sekcję [Active Documents](../../mfc/active-documents.md) .

  |Opcja|Opis|
  |------------|-----------------|
  |**Serwer aktywnego dokumentu**|Wskazuje, że aplikacja może tworzyć aktywne dokumenty i zarządzać nimi. W przypadku wybrania tej opcji należy określić rozszerzenie pliku aktywnego serwera dokumentów w polu **rozszerzenie pliku** na stronie [ciągi szablonu dokumentu](../../mfc/reference/document-template-strings-mfc-application-wizard.md) kreatora. Aby uzyskać więcej informacji, zobacz [serwery dokumentów aktywnych](../../mfc/active-document-servers.md) .|
  |**Kontener aktywnego dokumentu**|Wskazuje, że aplikacja może zawierać aktywne dokumenty w ramce. Dokumenty aktywne mogą obejmować na przykład dokumenty programu Internet Explorer lub dokumenty pakietu Office, takie jak pliki Microsoft Word lub arkusze kalkulacyjne programu Excel. Aby uzyskać więcej informacji, zobacz sekcję [zawieranie dokumentów aktywnych](../../mfc/active-document-containment.md) .|
  |**Obsługa plików złożonych**|Nie wykonuje serializacji dokumentów aplikacji kontenera przy użyciu formatu pliku złożonego. Ta opcja wymusza ładowanie całego pliku zawierającego obiekty do pamięci. Zapisywanie przyrostowe w pojedynczych obiektach jest niedostępne. Jeśli jeden obiekt zostanie zmieniony, a następnie zapisany, wszystkie obiekty w pliku są zapisywane.|

## <a name="see-also"></a>Zobacz też

[Kreator aplikacji MFC](../../mfc/reference/mfc-application-wizard.md)
