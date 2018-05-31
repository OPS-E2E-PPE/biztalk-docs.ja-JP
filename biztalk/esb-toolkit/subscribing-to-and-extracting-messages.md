---
title: サブスクライブおよびメッセージの抽出 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e7fbc17-44d6-4cc5-a266-b54256e7b453
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22d5a7f6065e8040e390947d44510bb7414e8e10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294722"
---
# <a name="subscribing-to-and-extracting-messages"></a>サブスクライブおよびメッセージの抽出
オーケストレーションは、サブスクライブして、ESB フォールト メッセージからメッセージを抽出するためのコードを含めることができます。 たとえば、次のコードでは、 **GetMessage**と**GetException**入力したメッセージの 2 つの厳密に抽出する方法、および**System.Exception** ESB からオブジェクトエラー メッセージ。  
  
```csharp  
// Retrieve two messages from the fault message.  
requestMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessage(  
                                    faultMsg, "ApprovedRequest");  
deniedMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessage(  
                                    faultMsg, "DeniedRequest");  
  
// Retrieve the System.Exception object.  
newExc = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetException(  
                                    faultMsg);  
```  
  
 型のないメッセージを抽出するには、次のコードを使用して、 **GetMessages**すべてのメッセージを抽出し、それらを反復処理するメソッド。  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.MessageCollection msgs;  
msgs = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessages(faultMsg);  
System.Xml.XmlDocument tmpMsg;  
while (msgs.MoveNext())  
{  
  tmpMsg = msgs.Current;  
}  
```