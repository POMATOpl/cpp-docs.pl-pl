---
description: 'Dowiedz się więcej na temat: TN048: pisanie programów instalacyjnych i administracyjnych ODBC dla aplikacji baz danych MFC'
title: 'TN048: pisanie programów instalacyjnych i administracyjnych ODBC dla aplikacji baz danych MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
ms.openlocfilehash: bca8616bae8f7243b9e66b2eccc980afa3865842
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215108"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: pisanie programów instalacyjnych i administracyjnych ODBC dla aplikacji baz danych MFC

> [!NOTE]
> Następująca Uwaga techniczna nie została zaktualizowana, ponieważ została najpierw uwzględniona w dokumentacji online. W związku z tym niektóre procedury i tematy mogą być nieaktualne lub nieprawidłowe. Aby uzyskać najnowsze informacje, zalecamy wyszukiwanie tematu zainteresowania w indeksie dokumentacji online.

Aplikacje korzystające z klas baz danych MFC będą potrzebować programu instalacyjnego, który instaluje składniki ODBC. Mogą również potrzebować programu administracyjnego ODBC, który będzie pobierać informacje o dostępnych sterownikach, aby określić sterowniki domyślne i skonfigurować źródła danych. Ta Uwaga opisuje użycie interfejsu API Instalatora ODBC do zapisywania tych programów.

## <a name="writing-an-odbc-setup-program"></a><a name="_mfcnotes_writing_an_odbc_setup_program"></a> Pisanie programu instalacyjnego ODBC

Aplikacja bazy danych MFC wymaga, aby Menedżer sterowników ODBC (ODBC.DLL) i sterowniki ODBC mogły uzyskać dostęp do źródeł danych. Wiele sterowników ODBC wymaga również dodatkowych bibliotek DLL sieci i komunikacji. Większość sterowników ODBC jest dostarczana z programem instalacyjnym, który zainstaluje wymagane składniki ODBC. Deweloperzy aplikacji korzystający z klas baz danych MFC mogą:

- Zależą od programów instalacyjnych specyficznych dla sterownika na potrzeby instalowania składników ODBC. Nie będzie to wymagać dalszej pracy nad częścią dewelopera — możesz po prostu ponownie przeprowadzić dystrybucję programu instalacyjnego sterownika.

- Alternatywnie można napisać własny program instalacyjny, który zainstaluje Menedżera sterowników i sterownik.

Interfejs API Instalatora ODBC może służyć do zapisywania programów instalacyjnych specyficznych dla aplikacji. Funkcje w interfejsie API Instalatora są implementowane przez bibliotekę DLL Instalatora ODBC — ODBCINST.DLL w 16-bitowym systemie Windows i ODBCCP32.DLL w systemie Win32. Aplikacja może wywołać `SQLInstallODBC` w bibliotece DLL Instalatora, która zainstaluje Menedżera sterowników ODBC, sterowniki ODBC i wszystkie wymagane translatory. Następnie rejestruje zainstalowane sterowniki i translatory w pliku ODBCINST.INI (lub rejestrze w systemie NT). `SQLInstallODBC` wymaga pełnej ścieżki do ODBC. Plik INF zawierający listę sterowników do zainstalowania oraz Opis plików wchodzących w skład poszczególnych sterowników. Zawiera również podobne informacje o Menedżerze sterowników i translatorach. Database. Pliki INF są zwykle dostarczane przez deweloperów sterowników.

Program może również instalować poszczególne składniki ODBC. Aby zainstalować Menedżera sterowników, program najpierw wywołuje `SQLInstallDriverManager` w bibliotece DLL Instalatora, aby uzyskać katalog docelowy Menedżera sterowników. Jest to zazwyczaj katalog, w którym znajdują się biblioteki DLL systemu Windows. Program używa następnie informacji w sekcji [ODBC Driver Manager] sterownika ODBC. Plik INF, aby skopiować Menedżera sterowników i powiązane pliki z dysku instalacyjnego do tego katalogu. Aby zainstalować pojedynczy sterownik, program najpierw wywołuje `SQLInstallDriver` w bibliotece DLL Instalatora w celu dodania specyfikacji sterownika do pliku ODBCINST.INI (lub rejestru na serwerze NT). `SQLInstallDriver` zwraca katalog docelowy sterownika — zazwyczaj katalog, w którym znajdują się biblioteki DLL systemu Windows. Program używa następnie informacji w sekcji sterownika ODBC. Plik INF, aby skopiować bibliotekę DLL sterownika i powiązane pliki z dysku instalacyjnego do tego katalogu.

Aby uzyskać więcej informacji na temat ODBC. INF, ODBCINST.INI i korzystania z interfejsu API Instalatora, zobacz *informacje dotyczące programisty* zestawu ODBC SDK, Rozdział 19, instalowanie oprogramowania ODBC.

## <a name="writing-an-odbc-administrator"></a><a name="_mfcnotes_writing_an_odbc_administrator"></a> Pisanie administratora ODBC

Aplikacja bazy danych MFC może skonfigurować i skonfigurować źródła danych ODBC na jeden z dwóch sposobów:

- Użyj Administratora ODBC (dostępnego jako program lub jako element Panelu sterowania).

- Utwórz własny program, aby skonfigurować źródła danych.

Program, który konfiguruje źródła danych, tworzy wywołania funkcji do biblioteki DLL Instalatora. Biblioteka DLL Instalatora wywołuje bibliotekę DLL Instalatora w celu skonfigurowania źródła danych. Dla każdego sterownika istnieje jedna biblioteka DLL konfiguracji; może to być sama Biblioteka DLL sterownika lub oddzielna Biblioteka DLL. Biblioteka DLL Instalatora programu prosi użytkownika o informacje, które sterownik musi połączyć się ze źródłem danych i translatorem domyślnym, jeśli jest obsługiwany. Następnie wywołuje biblioteki DLL Instalatora i interfejsy API systemu Windows, aby zarejestrować te informacje w pliku ODBC.INI (lub rejestrze).

Aby wyświetlić okno dialogowe, w którym użytkownik może dodawać, modyfikować i usuwać źródła danych, program wywołuje `SQLManageDataSources` w bibliotece DLL Instalatora. Ta funkcja jest wywoływana, gdy biblioteka DLL Instalatora jest wywoływana z panelu sterowania. Aby dodać, zmodyfikować lub usunąć źródło danych, program `SQLManageDataSources` wywołuje `ConfigDSN` konfigurację dll dla sterownika skojarzonego z tym źródłem danych. Aby bezpośrednio dodawać, modyfikować lub usuwać źródła danych, program wywołuje `SQLConfigDataSource` w bibliotece DLL Instalatora. Program przekazuje nazwę źródła danych i opcję, która określa akcję do wykonania. `SQLConfigDataSource` wywołania `ConfigDSN` w bibliotece DLL Instalatora i przekazuje je do argumentów z `SQLConfigDataSource` .

Aby uzyskać więcej informacji, zobacz Dokumentacja zestawu ODBC SDK *programisty,* rozdział 23, dokumentacja funkcji DLL instalatora oraz rozdział 24, dokumentacja funkcji DLL Instalatora.

## <a name="see-also"></a>Zobacz też

[Uwagi techniczne według numeru](../mfc/technical-notes-by-number.md)<br/>
[Uwagi techniczne według kategorii](../mfc/technical-notes-by-category.md)
