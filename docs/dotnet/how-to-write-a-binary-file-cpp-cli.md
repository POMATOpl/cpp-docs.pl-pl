---
title: 'Porady: wpisywanie danych do pliku binarnego (C + +/ CLI) | Dokumentacja firmy Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- binary files, writing in C++
- files [C++], binary
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 66d4c46fa82713e55ce39880f5e379cafcdf9ec6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-binary-file-ccli"></a>Porady: wpisywanie danych do pliku binarnego (C++/CLI)
Poniższy przykład kodu pokazuje, zapisywania do pliku danych binarnych. Dwie klasy z <xref:System.IO> przestrzeni nazw są używane: <xref:System.IO.FileStream> i <xref:System.IO.BinaryWriter>. <xref:System.IO.FileStream>reprezentuje rzeczywisty plik, podczas gdy <xref:System.IO.BinaryWriter> zapewnia interfejs do strumienia, który umożliwia dostęp do danych binarnych.  
  
 Poniższy przykład kodu zapisuje plik zawierający liczb całkowitych w formacie binarnym. Ten plik można odczytać kodu z [porady: odczytywanie pliku binarnego (C + +/ CLI)](../dotnet/how-to-read-a-binary-file-cpp-cli.md).  
  
## <a name="example"></a>Przykład  
  
```  
// binary_write.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   array<Int32>^ data = {1, 2, 3, 10000};  
  
   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);  
   BinaryWriter^ w = gcnew BinaryWriter(fs);  
  
   try   
   {  
      Console::WriteLine("writing data to file:");  
      for (int i=0; i<data->Length; i++)  
      {  
         Console::WriteLine(data[i]);  
         w->Write(data[i]);  
      }  
   }  
   catch (Exception^)   
   {  
     Console::WriteLine("data could not be written");  
     fs->Close();  
     return -1;  
   }  
  
   fs->Close();  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Plik i strumienia I-O](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)