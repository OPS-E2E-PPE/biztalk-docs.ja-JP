---
title: 動的ポートに値を割り当てる式を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic send ports, variables
- send ports, dynamic
ms.assetid: 6bdb937c-8702-43ff-914a-a02adc88658b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88e049772fcdcb9c5b15f9647d126c74faacf407
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333474"
---
# <a name="use-expressions-to-assign-values-to-dynamic-ports"></a><span data-ttu-id="553f1-102">動的ポートに値を割り当てる式を使用</span><span class="sxs-lookup"><span data-stu-id="553f1-102">Use Expressions to Assign Values to Dynamic Ports</span></span>

## <a name="assign-values"></a><span data-ttu-id="553f1-103">値を割り当てる</span><span class="sxs-lookup"><span data-stu-id="553f1-103">Assign values</span></span>
<span data-ttu-id="553f1-104">送信ポートが動的としてマークするは、式図形で使用するポートの URI を格納する文字列型の変数の値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="553f1-104">If a send port is marked as dynamic, you can assign to it the value of some variable of type string that contains the URI of the port you want to use in the Expression shape.</span></span> <span data-ttu-id="553f1-105">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="553f1-105">For example,</span></span>  
  
```  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="mailto:johnd@contoso.com";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)=@"file://C:\MyLocation\%SourceFileName%.xml";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)=@"msmq://.\private$\MyQueue";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="http://MyOrder.contoso.com";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="ftp://MyServer/MyDirectory/%MessageID%.xml";  
```  
  
 <span data-ttu-id="553f1-106">送信メッセージにプロパティをさらに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="553f1-106">Then you can further assign the properties to the outgoing messages.</span></span> <span data-ttu-id="553f1-107">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="553f1-107">For example,</span></span>  
  
```  
MyOutgoingMessage(SMTP.Subject)="Purcahse Order Received";  
MyOutgoingMessage(FILE.ReceivedFileName)="MyFileName.xml";  
MyOutgoingMessage(FTP.UserName)="MyUserName";  
MyOutgoingMessage(FTP.Password)="MyPassword";  
MyOutgoingMessage((MSMQ.Transactional)=true;  
```  
  
## <a name="see-also"></a><span data-ttu-id="553f1-108">参照</span><span class="sxs-lookup"><span data-stu-id="553f1-108">See Also</span></span>  
[<span data-ttu-id="553f1-109">ファイル アダプタ構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="553f1-109">Restrictions when configuring the File adapter</span></span>](restrictions-when-configuring-the-file-adapter.md)