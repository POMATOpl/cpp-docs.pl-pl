---
title: Zarządzanie bibliotekami za pomocą vcpkg
description: Dowiedz się, jak zarządzać bibliotekami przy użyciu vcpkg w systemach Windows, macOS i Linux.
ms.date: 12/11/2020
ms.technology: cpp-ide
ms.openlocfilehash: 88f8bc1cff7b4b04f5e38b5018676e313383733f
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684269"
---
# <a name="manage-libraries-with-vcpkg"></a>Zarządzanie bibliotekami za pomocą vcpkg

Po [zainstalowaniu programu vcpkg](install-vcpkg.md)można go używać do uzyskiwania i kompilowania bibliotek na komputerze lokalnym.

## <a name="search-the-list-of-available-libraries"></a>Przeszukaj listę dostępnych bibliotek

### <a name="windows"></a>[Windows](#tab/windows)

Aby zobaczyć, jakie pakiety są dostępne, wpisz **`vcpkg search`** w wierszu polecenia.

To polecenie wylicza pliki kontrolki w *`vcpkg/ports`* podfolderach. Zobaczysz listę w następujący sposób:

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Można filtrować według wzorca, na przykład **`vcpkg search ta`** :

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-local-machine"></a>Instalowanie biblioteki na komputerze lokalnym

Po otrzymaniu nazwy biblioteki przy użyciu programu **`vcpkg search`** można **`vcpkg install`** pobrać bibliotekę i skompilować ją. vcpkg używa biblioteki Portfile w katalogu *portów* . Jeśli tryplet nie jest określony, vcpkg instaluje i kompiluje dla domyślnego tryplet dla platformy docelowej: x86-Windows, x64-Linux. CMAKE lub x64-OSX. CMAKE.

W przypadku bibliotek systemu Linux vcpkg zależy od instalacji programu na komputerze lokalnym. W macOS, vcpkg używa Clang.

Gdy Portfile określa zależności, vcpkg pobiera i instaluje je. Po pobraniu vcpkg kompiluje bibliotekę przy użyciu tego samego systemu kompilacji, w którym jest używana biblioteka. Projekty programu MSBuild CMake i (w systemie Windows) są preferowane, ale jest obsługiwane wraz z jakimkolwiek innym systemem kompilacji. Jeśli vcpkg nie może znaleźć określonego systemu kompilacji na maszynie lokalnej, pobiera i instaluje go.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

W przypadku projektów CMake Użyj, `CMAKE_TOOLCHAIN_FILE` Aby udostępnić biblioteki z `find_package()` . Na przykład w systemie Linux lub macOS:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake
```

W systemie Windows:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg\scripts\buildsystems\vcpkg.cmake
```

Niektóre biblioteki obejmują opcje instalowalne. Na przykład podczas wyszukiwania biblioteki zwinięcie zostanie również wyświetlona lista obsługiwanych opcji w nawiasach kwadratowych:

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

W tym przypadku nawiasy kwadratowe **`[`** i **`]`** są literałami, a nie metaznakami.

W wierszu polecenia można określić konkretną opcję instalacji. Aby na przykład zainstalować biblioteki dla programu zwinięcie przy użyciu domyślnego zaplecza protokołu SSL dla systemu Windows, użyj **`vcpkg install curl[ssl]:x86-windows`** polecenia. Polecenie instaluje wszystkie wymagane wymagania wstępne, w tym bibliotekę podstawową, w razie potrzeby:

```cmd
> vcpkg list
curl:x86-windows            7.68.0-3   A library for transferring data with URLs
curl[non-http]:x86-windows             Enables protocols beyond HTTP/HTTPS/HTTP2
curl[ssl]:x86-windows                  Default SSL backend
curl[sspi]:x86-windows                 SSPI support
curl[winssl]:x86-windows               SSL support (Secure Channel / "WinSSL")
zlib:x86-windows            1.2.11-6   A compression library
```

### <a name="macos"></a>[macOS](#tab/macos)

Aby zobaczyć, jakie pakiety są dostępne, przejdź do katalogu głównego vcpkg i wprowadź **`./vcpkg search`** w terminalu.

To polecenie wylicza pliki kontrolki w *`vcpkg/ports`* podfolderach. Zobaczysz listę w następujący sposób:

```Terminal
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Można filtrować według wzorca, na przykład **`vcpkg search ta`** :

```Terminal
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-computer"></a>Instalowanie biblioteki na komputerze

Po otrzymaniu nazwy biblioteki przy użyciu programu **`vcpkg search`** można **`vcpkg install`** pobrać bibliotekę i skompilować ją. vcpkg używa biblioteki Portfile w katalogu *portów* . Jeśli tryplet nie jest określony, vcpkg instaluje i kompiluje dla domyślnego tryplet dla platformy docelowej: x86-Windows, x64-Linux. CMAKE lub x64-OSX. CMAKE.

W przypadku bibliotek systemu Linux vcpkg zależy od instalacji programu na komputerze lokalnym. W macOS, vcpkg używa Clang.

Gdy Portfile określa zależności, vcpkg pobiera i instaluje je. Po pobraniu vcpkg kompiluje bibliotekę przy użyciu tego samego systemu kompilacji, w którym jest używana biblioteka. Projekty programu MSBuild CMake i (w systemie Windows) są preferowane, ale jest obsługiwane wraz z jakimkolwiek innym systemem kompilacji. Jeśli vcpkg nie może znaleźć określonego systemu kompilacji na maszynie lokalnej, pobiera i instaluje go.

```Terminal
$ ./vcpkg install boost

The following packages will be built and installed:
    boost:x86-macos
  * bzip2:x86-macos
  * zlib:x86-macos
Additional packages (*) will be installed to complete this operation.
```

W przypadku projektów CMake Użyj, `CMAKE_TOOLCHAIN_FILE` Aby udostępnić biblioteki z `find_package()` . Na przykład:

```Terminal
cmake .. -DCMAKE_TOOLCHAIN_FILE=./vcpkg/scripts/buildsystems/vcpkg.cmake
```

Niektóre biblioteki obejmują opcje instalowalne. Na przykład podczas wyszukiwania biblioteki zwinięcie zostanie również wyświetlona lista obsługiwanych opcji w nawiasach kwadratowych:

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

W tym przypadku nawiasy kwadratowe **`[`** i **`]`** są literałami, a nie metaznakami.

W wierszu polecenia można określić konkretną opcję instalacji. Aby na przykład zainstalować biblioteki dla programu zwinięcie przy użyciu domyślnego zaplecza protokołu SSL, użyj **`./vcpkg install curl[ssl]`** polecenia. Polecenie instaluje wszystkie wymagane wymagania wstępne, w tym bibliotekę podstawową, w razie potrzeby.

### <a name="linux"></a>[Linux](#tab/linux)

Aby zobaczyć, jakie pakiety są dostępne, przejdź do katalogu głównego vcpkg w powłoce, a następnie wprowadź **`./vcpkg search`** .

To polecenie wylicza pliki kontrolki w *`vcpkg/ports`* podfolderach. Zobaczysz listę w następujący sposób:

```shell
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Można filtrować według wzorca, na przykład **`./vcpkg search ta`** :

```shell
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-linux-machine"></a>Instalowanie biblioteki na komputerze z systemem Linux

Po otrzymaniu nazwy biblioteki przy użyciu programu **`./vcpkg search`** można **`/vcpkg install`** pobrać bibliotekę i skompilować ją. vcpkg używa biblioteki Portfile w *`ports`* katalogu. Jeśli tryplet nie jest określony, vcpkg instaluje i kompiluje dla domyślnej tryplet dla platformy docelowej, takiej jak x64-Linux. CMAKE.

W przypadku bibliotek systemu Linux vcpkg zależy od instalacji programu na komputerze lokalnym.

Gdy Portfile określa zależności, vcpkg pobiera i instaluje je. Po pobraniu vcpkg kompiluje bibliotekę przy użyciu tego samego systemu kompilacji, w którym jest używana biblioteka. Projekty CMake są preferowane, ale jest obsługiwane wraz z jakimkolwiek innym systemem kompilacji. Jeśli vcpkg nie może znaleźć określonego systemu kompilacji na maszynie lokalnej, pobiera i instaluje go.

```shell
$ ./vcpkg install boost:x64-linux

The following packages will be built and installed:
    boost:x64-linux
  * bzip2:x64-linux
  * zlib:x64-linux
Additional packages (*) will be installed to complete this operation.
```

W przypadku projektów CMake Użyj, `CMAKE_TOOLCHAIN_FILE` Aby udostępnić biblioteki z `find_package()` . Na przykład:

```shell
cmake .. -DCMAKE_TOOLCHAIN_FILE=./vcpkg/scripts/buildsystems/vcpkg.cmake
```

Niektóre biblioteki obejmują opcje instalowalne. Na przykład podczas wyszukiwania biblioteki zwinięcie zostanie również wyświetlona lista obsługiwanych opcji w nawiasach kwadratowych:

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

W tym przypadku nawiasy kwadratowe **`[`** i **`]`** są literałami, a nie metaznakami.

W wierszu polecenia można określić konkretną opcję instalacji. Aby na przykład zainstalować biblioteki dla programu zwinięcie przy użyciu domyślnego zaplecza protokołu SSL, użyj **`./vcpkg install curl[ssl]`** polecenia. Polecenie instaluje wszystkie wymagane wymagania wstępne, w tym bibliotekę podstawową, w razie potrzeby.

---

## <a name="list-the-libraries-already-installed"></a>Lista bibliotek zainstalowanych już

Po zainstalowaniu niektórych bibliotek możesz użyć **`vcpkg list`** polecenia w systemie Windows, aby zobaczyć, co masz. Polecenia systemu Linux i macOS są analogiczne.

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="target-linux-from-windows-via-wsl"></a>Ukierunkowane na system Linux z systemu Windows za pośrednictwem WSL

Pliki binarne systemu Linux można tworzyć na komputerze z systemem Windows za pomocą podsystemu Windows dla systemów Linux lub WSL. Postępuj zgodnie z instrukcjami, aby [skonfigurować WSL w systemie Windows 10](/windows/wsl/install-win10). Następnie skonfiguruj go za pomocą [rozszerzenia programu Visual Studio dla systemu Linux](https://devblogs.microsoft.com/cppblog/targeting-windows-subsystem-for-linux-from-visual-studio/). Można umieścić wszystkie skompilowane biblioteki dla systemów Windows i Linux w tym samym folderze. Są one dostępne zarówno w systemie Windows, jak i w WSL.

## <a name="export-compiled-binaries-and-headers"></a><a name="export_binaries_per_project"></a> Eksportuj skompilowane pliki binarne i nagłówki

Wszyscy członkowie zespołu mogą pobierać i kompilować wspólne biblioteki. Pojedynczy członek zespołu może użyć polecenia, **`vcpkg export`** Aby utworzyć wspólny plik zip plików binarnych i nagłówków lub pakiet NuGet. Następnie można łatwo udostępnić go innym członkom zespołu.

## <a name="updateupgrade-installed-libraries"></a>Aktualizowanie/uaktualnianie zainstalowanych bibliotek

Wykaz publiczny jest bieżąco z najnowszymi wersjami bibliotek. Aby określić, które biblioteki lokalne są nieaktualne, użyj programu **`vcpkg update`** . Gdy wszystko będzie gotowe do zaktualizowania kolekcji portów do najnowszej wersji wykazu publicznego, uruchom **`vcpkg upgrade`** polecenie. Automatycznie pobiera i odtwarza wszystkie zainstalowane biblioteki, które są nieaktualne.

Domyślnie **`vcpkg upgrade`** polecenie wyświetla tylko te biblioteki, które są nieaktualne; nie uaktualnia ich. Aby faktycznie uaktualnić biblioteki, użyj **`--no-dry-run`** opcji.

```cmd
> vcpkg upgrade --no-dry-run
```

### <a name="upgrade-options"></a>Opcje uaktualniania

- **`--no-dry-run`**  Wykonaj uaktualnienie; gdy nie zostanie określony, polecenie wyświetla tylko listę nieaktualnych pakietów.
- **`--keep-going`**  Kontynuuj Instalowanie pakietów nawet wtedy, gdy jeden z nich nie powiedzie się.
- **`--triplet <t>`**  Ustaw wartość domyślną tryplet dla niekwalifikowanych pakietów.
- **`--vcpkg-root <path>`**  Określ katalog vcpkg, który ma być używany zamiast bieżącego katalogu lub katalogu narzędzi.

### <a name="upgrade-example"></a>Przykład uaktualnienia

Poniższy przykład pokazuje, jak uaktualnić tylko określone biblioteki w systemie Windows. Polecenia systemu Linux i macOS są analogiczne. vcpkg automatycznie ściąga w zależności od potrzeb.

```cmd
c:\users\username\vcpkg> vcpkg upgrade tiny-dnn:x86-windows zlib
The following packages are up-to-date:
   tiny-dnn:x86-windows

The following packages will be rebuilt:
    * libpng[core]:x86-windows
    * tiff[core]:x86-windows
      zlib[core]:x86-windows
Additional packages (*) will be modified to complete this operation.
If you are sure you want to rebuild the above packages, run this command with the --no-dry-run option.
```

## <a name="contribute-new-libraries"></a>Tworzenie nowych bibliotek

Możesz dołączyć wszystkie biblioteki, które lubisz w swojej kolekcji portów prywatnych. Aby zasugerować nową bibliotekę wykazu publicznego, Otwórz problem na [stronie problemu vcpkg usługi GitHub](https://github.com/Microsoft/vcpkg/issues).

## <a name="remove-a-library"></a>Usuwanie biblioteki

Wpisz **`vcpkg remove`** , aby usunąć zainstalowaną bibliotekę. Jeśli zależą od niej inne biblioteki, zostanie wyświetlony monit o ponowne uruchomienie polecenia z **`--recurse`** , co spowoduje usunięcie wszystkich bibliotek podrzędnych.

## <a name="see-also"></a>Zobacz także

[vcpkg: Menedżer pakietów języka C++ dla systemów Windows, Linux i macOS](./vcpkg.md)\
[vcpkg w serwisie GitHub](https://github.com/Microsoft/vcpkg)\
[Zainstaluj vcpkg](install-vcpkg.md)\
[Integruj vcpkg](integrate-vcpkg.md)\
[vcpkg — dokumentacja wiersza polecenia](vcpkg-command-line-reference.md)\
[Szybki Start](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Często zadawane pytania](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)\
[Przykład instalowania i używania pakietów: SQLite](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md)
