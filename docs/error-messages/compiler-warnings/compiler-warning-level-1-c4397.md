---
title: "Kompilatora (poziom 1) ostrzeżenie C4397 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4397
dev_langs: C++
helpviewer_keywords: C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 85d15a25bf55bcc63f0506d74cf4268290c60905
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4397"></a>Kompilatora (poziom 1) ostrzeżenie C4397
DefaultCharSetAttribute jest ignorowana.  
  
 <xref:System.Runtime.InteropServices.DefaultCharSetAttribute>jest ignorowana przez kompilator języka Visual C++. Aby określić zestaw znaków dla biblioteki DLL, użyj opcji CharSet DllImport. Aby uzyskać więcej informacji, zobacz [za pomocą międzyoperacyjności języka C++ (niejawna funkcja PInvoke)](../../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4397.  
  
```  
// C4397.cpp  
// compile with: /W1 /c /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[module:DefaultCharSetAttribute(CharSet::Unicode)];   // C4397  
  
[DllImport("kernel32", EntryPoint="CloseHandle", CharSet=CharSet::Unicode)]   // OK  
extern "C" bool ImportDefault(IntPtr hObject);  
  
public ref class MySettingVC {  
public:  
   void method() {  
      ImportDefault(IntPtr::Zero);  
   }  
};  
  
[StructLayout(LayoutKind::Explicit)]  
public ref struct StructDefault1{};  
  
public ref class ClassDefault1{};  
```