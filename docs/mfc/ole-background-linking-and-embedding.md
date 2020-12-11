---
description: 'Dowiedz się więcej na temat: tło OLE: łączenie i osadzanie'
title: 'Podstawy OLE: łączenie i osadzanie'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
ms.openlocfilehash: 05bd51c11cadfc3220f23db9098db9f07703a814
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112222"
---
# <a name="ole-background-linking-and-embedding"></a>Podstawy OLE: łączenie i osadzanie

Za pomocą polecenia Wklej w aplikacji kontenera można utworzyć osadzony składnik lub osadzony element. Dane źródłowe dla osadzonego elementu są przechowywane jako część dokumentu OLE, który go zawiera. W ten sposób plik dokumentu dla dokumentu edytora tekstów może zawierać tekst i może zawierać mapy bitowe, wykresy, formuły lub inne typy danych.

Mechanizm OLE zapewnia inny sposób dołączania danych z innej aplikacji: Tworzenie połączonego składnika, elementu połączonego lub linku. Kroki tworzenia połączonego elementu są podobne do tych w przypadku tworzenia osadzonego elementu, z tą różnicą, że zamiast polecenia Wklej użyto polecenia Wklej łącze. W przeciwieństwie do składnika osadzonego, połączony składnik przechowuje ścieżkę do oryginalnych danych, często w osobnym pliku.

Na przykład jeśli pracujesz w dokumencie edytora tekstów i utworzysz połączony element do niektórych komórek arkusza kalkulacyjnego, dane połączonego elementu są przechowywane w oryginalnym dokumencie arkusza kalkulacyjnego. Dokument edytora wyrazów zawiera tylko informacje określające, gdzie można znaleźć element, czyli zawiera link do oryginalnego dokumentu arkusza kalkulacyjnego. Po dwukrotnym kliknięciu komórek aplikacja arkusza kalkulacyjnego zostanie uruchomiona i oryginalny dokument arkusza kalkulacyjnego zostanie załadowany z lokalizacji, w której został zapisany.

Każdy element OLE, niezależnie od tego, czy jest osadzony lub połączony, ma skojarzony typ na podstawie aplikacji, która ją utworzyła. Na przykład element Microsoft Paintbrush jest jednym typem elementu, a element programu Microsoft Excel jest innym typem. Niektóre aplikacje mogą jednak utworzyć więcej niż jeden typ elementu. Na przykład program Microsoft Excel może tworzyć elementy arkusza, elementy wykresu i elementy makr. Każdy z tych elementów może być jednoznacznie zidentyfikowany przez system przy użyciu identyfikatora klasy lub identyfikatora **CLSID**.

## <a name="see-also"></a>Zobacz też

[Tło OLE](ole-background.md)<br/>
[Tło OLE: kontenery i serwery](ole-background-containers-and-servers.md)<br/>
[Kontenery: elementy klienta](containers-client-items.md)<br/>
[Serwery: elementy serwera](servers-server-items.md)
