---
title: 'Porady: odczytywanie pliku tekstowego (C + +/ CLI) | Dokumentacja firmy Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- reading text files
- text files, reading
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 68add197649dd494225787775ab772e8ffc0fc89
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-read-a-text-file-ccli"></a>Porady: odczytywanie pliku tekstowego (C++/CLI)
Poniższy przykład kodu pokazuje, jak otwieranie i odczyt plików tekstowych jeden wiersz jednocześnie, za pomocą <xref:System.IO.StreamReader> klasy, która jest zdefiniowana w <xref:System.IO?displayProperty=fullName> przestrzeni nazw. Wystąpienie tej klasy jest używany do otwierania pliku tekstowego, a następnie <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> metoda służy do pobierania każdego wiersza.  
  
 Ten przykładowy kod odczytuje plik, który ma nazwę textfile.txt i zawiera tekst. Aby uzyskać informacje dotyczące tego typu plików, zobacz [porady: wpisywanie tekstu do pliku (C + +/ CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md).  
  
## <a name="example"></a>Przykład  
  
```  
// text_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ fileName = "textfile.txt";  
   try   
   {  
      Console::WriteLine("trying to open file {0}...", fileName);  
      StreamReader^ din = File::OpenText(fileName);  
  
      String^ str;  
      int count = 0;  
      while ((str = din->ReadLine()) != nullptr)   
      {  
         count++;  
         Console::WriteLine("line {0}: {1}", count, str );  
      }  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("file '{0}' not found", fileName);  
      else  
         Console::WriteLine("problem reading file '{0}'", fileName);  
   }  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Plik i strumienia I-O](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [.NET programowania w języku C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)