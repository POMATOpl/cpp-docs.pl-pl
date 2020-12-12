---
description: 'Dowiedz się więcej na temat: @ (Określ plik odpowiedzi kompilatora)'
title: '@ (Określ plik odpowiedzi kompilatora)'
ms.date: 11/04/2016
f1_keywords:
- '@'
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
ms.openlocfilehash: bd2859f7973723d93594693902e92ac3530d73ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182895"
---
# <a name="-specify-a-compiler-response-file"></a>@ (Określ plik odpowiedzi kompilatora)

Określa plik odpowiedzi kompilatora.

## <a name="syntax"></a>Składnia

> **\@**<em>response_file</em>

## <a name="arguments"></a>Argumenty

*response_file*<br/>
Plik tekstowy zawierający polecenia kompilatora.

## <a name="remarks"></a>Uwagi

Plik odpowiedzi może zawierać wszystkie polecenia, które można określić w wierszu polecenia. Może to być przydatne, jeśli argumenty wiersza polecenia przekraczają 127 znaków.

Nie można określić **\@** opcji z poziomu pliku odpowiedzi. Oznacza to, że plik odpowiedzi nie może osadzić innego pliku odpowiedzi.

W wierszu polecenia można określić dowolną liczbę opcji pliku odpowiedzi (np `@respfile.1 @respfile.2` .).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

- Plik odpowiedzi nie może być określony w środowisku deweloperskim i musi być określony w wierszu polecenia.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Nie można programowo zmienić tej opcji kompilatora.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)
