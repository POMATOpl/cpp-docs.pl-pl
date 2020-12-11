---
description: Dowiedz się więcej na temat klas modułów ATL
title: Klasy modułów ALT
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 16c38a6a38f4179e5846a445bd9573e7dc4500f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163304"
---
# <a name="atl-module-classes"></a>Klasy modułów ALT

W tym temacie omówiono klasy modułów, które były nowe w ATL 7,0.

## <a name="ccommodule-replacement-classes"></a>CComModule klasy zastępcze

Użyto wcześniejszych wersji biblioteki ATL `CComModule` . W przypadku biblioteki ATL 7,0 `CComModule` Funkcja jest zastępowana przez kilka klas:

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) Zawiera informacje wymagane przez większość aplikacji, które korzystają z biblioteki ATL. Zawiera HINSTANCE modułu i wystąpienia zasobu.

- [CAtlComModule](../atl/reference/catlcommodule-class.md) Zawiera informacje wymagane przez klasy COM w ATL.

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) Zawiera informacje wymagane przez klasy okien w ATL.

- [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) Zawiera obsługę debugowania interfejsu.

- [CAtlModule](../atl/reference/catlmodule-class.md) Poniższe `CAtlModule` klasy pochodne są dostosowane do zawierania informacji wymaganych w konkretnym typie aplikacji. Większość elementów członkowskich w tych klasach można zastąpić:

  - [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) Używany w aplikacjach DLL. Zawiera kod dla eksportów standardowych.

  - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) Używany w aplikacjach EXE. Zapewnia kod wymagany w pliku EXE.

  - [Funkcja CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Zapewnia obsługę tworzenia usług systemu Windows NT i Windows 2000.

`CComModule` nadal jest dostępny w celu zapewnienia zgodności z poprzednimi wersjami.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>Przyczyny dystrybucji funkcji CComModule

Funkcje programu `CComModule` zostały przekazane do kilku nowych klas z następujących powodów:

- Zwiększ poziom funkcjonalności `CComModule` .

   Obsługa modelu COM, okna, debugowania interfejsów i funkcji specyficznych dla aplikacji (DLL lub EXE) znajduje się teraz w oddzielnych klasach.

- Automatycznie deklaruj globalne wystąpienie każdego z tych modułów.

   Globalne wystąpienie wymaganych klas modułów jest połączone z projektem.

- Usuń konieczność wywoływania metod Init i Term.

   Metody inicjacji i terminy zostały przeniesione do konstruktorów i destruktorów dla klas modułów; nie ma już potrzeby wywoływania funkcji init i Term.

## <a name="see-also"></a>Zobacz też

[Pojęcia](../atl/active-template-library-atl-concepts.md)<br/>
[Przegląd klas](../atl/atl-class-overview.md)
