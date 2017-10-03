---
title: "動的ポートに値を代入する式を使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic send ports, variables
- send ports, dynamic
ms.assetid: 6bdb937c-8702-43ff-914a-a02adc88658b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59c2d11b5da44e94beee914704f46ac6b0346e85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-expressions-to-assign-values-to-dynamic-ports"></a><span data-ttu-id="641a2-102">式を使用して動的ポートに値を割り当てる</span><span class="sxs-lookup"><span data-stu-id="641a2-102">Use Expressions to Assign Values to Dynamic Ports</span></span>

## <a name="assign-values"></a><span data-ttu-id="641a2-103">値を割り当てる</span><span class="sxs-lookup"><span data-stu-id="641a2-103">Assign values</span></span>
<span data-ttu-id="641a2-104">送信ポートを動的としてマークしている場合、式図形で使用するポートの URI を含む文字列型の変数の値を動的ポートに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="641a2-104">If a send port is marked as dynamic, you can assign to it the value of some variable of type string that contains the URI of the port you want to use in the Expression shape.</span></span> <span data-ttu-id="641a2-105">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="641a2-105">For example,</span></span>  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)=@"file://C:\MyLocation\%SourceFileName%.xml";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)=@"msmq://.\private$\MyQueue";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="http://MyOrder.contoso.com";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="ftp://MyServer/MyDirectory/%MessageID%.xml";  
```  
  
 <span data-ttu-id="641a2-106">さらに、送信メッセージにもプロパティを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="641a2-106">Then you can further assign the properties to the outgoing messages.</span></span> <span data-ttu-id="641a2-107">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="641a2-107">For example,</span></span>  
  
```  
MyOutgoingMessage(SMTP.Subject)="Purcahse Order Received";  
MyOutgoingMessage(FILE.ReceivedFileName)="MyFileName.xml";  
MyOutgoingMessage(FTP.UserName)="MyUserName";  
MyOutgoingMessage(FTP.Password)="MyPassword";  
MyOutgoingMessage((MSMQ.Transactional)=true;  
```  
  
## <a name="see-also"></a><span data-ttu-id="641a2-108">参照</span><span class="sxs-lookup"><span data-stu-id="641a2-108">See Also</span></span>  
[<span data-ttu-id="641a2-109">ファイル アダプタ構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="641a2-109">Restrictions when configuring the File adapter</span></span>](restrictions-when-configuring-the-file-adapter.md)