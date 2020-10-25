---
title: Wdrożenie środowiska Universal CRT
description: Dowiedz się, jak i gdzie należy wdrożyć uniwersalną bibliotekę CRT dla aplikacji.
ms.date: 10/23/2020
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
ms.openlocfilehash: 50ab23f3b0276b058685e9c9ef6634caf5a96186
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497209"
---
# <a name="universal-crt-deployment"></a>Wdrożenie środowiska Universal CRT

Z programu Visual Studio .NET za pośrednictwem Visual Studio 2013 każde główne wydanie kompilatora i narzędzi języka C++ zawiera nową, autonomiczną wersję biblioteki środowiska uruchomieniowego Microsoft C (CRT). Te autonomiczne wersje CRT były niezależne od i do różnych stopni, niezgodne ze sobą. Na przykład Biblioteka CRT używana przez program Visual Studio 2012 była w wersji 11 o nazwie msvcr110.dll i CRT używana przez Visual Studio 2013 była w wersji 12 o nazwie msvcr120.dll. Począwszy od programu Visual Studio 2015, nie jest to już przypadek. Program Visual Studio 2015 i nowsze wersje programu Visual Studio używają jednej uniwersalnej CRT.

Uniwersalny CRT (UCRT) jest składnikiem systemu operacyjnego Microsoft Windows. Jest on dołączony jako część systemu operacyjnego Windows 10 i Windows Server 2016 lub nowszego. UCRT jest dostępna przy użyciu Windows Update w starszych systemach operacyjnych, które są nadal w rozszerzonym obsłudze. Lokalne wdrożenie uniwersalnej CRT jest obsługiwane z pewnymi ograniczeniami.

## <a name="central-deployment"></a>Wdrażanie centralne

Preferowaną metodą centralnej instalacji uniwersalnej CRT jest użycie Windows Update Microsoft. Uniwersalny CRT to zalecana Aktualizacja dla wszystkich obsługiwanych systemów operacyjnych Microsoft Windows, więc domyślnie większość maszyn instaluje je w ramach procesu regularnej aktualizacji. Początkowa wersja uniwersalnej CRT została [KB2999226](https://support.microsoft.com/kb/2999226). Nowsza aktualizacja z różnymi poprawkami błędów została wprowadzona w programie [KB3118401](https://support.microsoft.com/kb/3118401)i wprowadzono dodatkowe aktualizacje z dodatkowymi poprawkami błędów i nowymi funkcjami. Aby zapoznać się z najnowszymi aktualizacjami, Wyszukaj [support.Microsoft.com](https://support.microsoft.com) dla uniwersalnego środowiska uruchomieniowego języka C lub uniwersalnej CRT.

Nie wszystkie komputery z systemem Microsoft Windows regularnie instalują aktualizacje przy użyciu programu Windows Update, a niektóre z nich mogą nie instalować wszystkich zalecanych aktualizacji. Aby obsługiwać korzystanie z aplikacji utworzonych przy użyciu narzędzi programu Visual Studio 2015 i nowszych C++ na tych maszynach, dostępne są uniwersalne, redystrybucyjne pliki do dystrybucji w trybie offline. Pliki redystrybucyjne mogą zostać pobrane z jednego z powyższych linków KB. Pakiet redystrybucyjny uniwersalnej CRT wymaga, aby komputer został zaktualizowany do bieżącego dodatku Service Pack. Na przykład pakiet redystrybucyjny dla systemu Windows 7 zostanie zainstalowany tylko w systemie Windows 7 z dodatkiem SP1, a nie w wersji RTM systemu Windows 7.

Ze względu na to, że uniwersalna CRT jest podstawową zależnością bibliotek języka C++, Visual C++ redystrybucyjna (VCRedist) instaluje początkową wersję uniwersalnej CRT (wersja 10.0.10240) na maszynach, na których jeszcze nie zainstalowano. Ta wersja jest wystarczająca do spełnienia zależności biblioteki C++. Jeśli aplikacja jest zależna od nowszej wersji uniwersalnej CRT, należy użyć Windows Update, aby zapewnić pełną aktualność maszyny, lub zainstalować tę wersję jawnie. Przed zainstalowaniem VCRedist najlepiej zainstalować środowisko uruchomieniowe uniwersalnego języka C za pośrednictwem Windows Update lub MSU, aby uniknąć potencjalnych ponownych uruchomień.

Nie wszystkie systemy operacyjne są odpowiednie dla najnowszej uniwersalnego środowiska uruchomieniowego C za pośrednictwem Windows Update. W systemie Windows 10 wdrożona centralnie wersja jest zgodna z wersją systemu operacyjnego. Aby dodatkowo zaktualizować uniwersalne środowisko uruchomieniowe języka C, należy zaktualizować system operacyjny. W przypadku systemu Windows Vista za pośrednictwem Windows 8.1 najnowsza dostępna wersja środowiska uruchomieniowego języka uniwersalnego C jest obecnie oparta na wersji aktualizacji z rocznicą systemu Windows 10 z dodatkowymi poprawkami (wersja 10.0.14393).

## <a name="local-deployment"></a>Wdrożenie lokalne

Obsługiwane jest lokalne wdrożenie uniwersalnej CRT, ale nie jest to zalecane ze względu na wydajność i bezpieczeństwo. Biblioteki DLL dla lokalnego wdrożenia są dołączane jako część Windows SDK w \\ \\ \\ podkatalogu UCRT biblioteki DLL Windows Kit 10 Redist \\ , architektura komputera. Wymagane biblioteki DLL obejmują ucrtbase.dll i zestaw bibliotek DLL usług przesyłania dalej APISet o nazwie API-ms-win- \* . dll. Zestaw bibliotek DLL wymaganych w poszczególnych systemach operacyjnych jest różny. Zdecydowanie zaleca się dołączenie wszystkich bibliotek DLL podczas wdrażania lokalnego.

Istnieją dwa ograniczenia dotyczące lokalnego wdrożenia, które mają być świadome:

- W systemie Windows 10, uniwersalna CRT w katalogu systemowym jest zawsze używana, nawet jeśli aplikacja zawiera kopię w aplikacji lokalnej uniwersalnej CRT. Jest ona prawdziwa nawet wtedy, gdy kopia lokalna jest nowsza, ponieważ Uniwersalny CRT jest podstawowym składnikiem systemu operacyjnego w systemie Windows 10.

- W wersjach systemu Windows starszych niż Windows 8 uniwersalnej CRT nie można spakować lokalnie z wtyczką, jeśli znajduje się w katalogu innym niż katalog pliku wykonywalnego aplikacji głównej. Biblioteki APISet przesyłania dalej nie mogą pomyślnie rozpoznać ucrtbase.dll w tym przypadku. Niektóre zalecane rozwiązania alternatywne obejmują:

  - Statyczne łączenie uniwersalnej CRT,
  - Centralne wdrażanie uniwersalnej CRT lub
  - Umieść pliki uniwersalnej CRT w tym samym katalogu, w którym znajduje się aplikacja.

## <a name="deployment-on-microsoft-windows-xp"></a>Wdrażanie w systemie Microsoft Windows XP

Programy Visual Studio 2015 i Visual Studio 2017 nadal obsługują programowanie oprogramowania do użytku w systemie Microsoft Windows XP. Aby zapewnić obsługę tego opracowania, wersja uniwersalnej CRT działa w systemie Microsoft Windows XP. System operacyjny Microsoft Windows XP nie jest już w większości ani rozszerzonej pomocy technicznej, więc centralne wdrożenie uniwersalnej CRT w systemie Microsoft Windows XP różni się od innych systemów operacyjnych.

Po zainstalowaniu pakietu redystrybucyjnego Visual C++ w systemie Windows XP program bezpośrednio instaluje uniwersalne środowisko CRT i wszystkie jego zależności w katalogu systemowym. Nie jest on instalowany ani zależał od żadnej Windows Update. Redystrybucyjne moduły scalania, pliki Microsoft_VC w*wersji*_CRT_ \* . MSM, wykonaj te same czynności.

Lokalne wdrożenie uniwersalnej CRT w systemie Windows XP jest takie samo jak w przypadku innych obsługiwanych systemów operacyjnych.

## <a name="see-also"></a>Zobacz też

- [Wdrożenie w Visual C++](deployment-in-visual-cpp.md)
