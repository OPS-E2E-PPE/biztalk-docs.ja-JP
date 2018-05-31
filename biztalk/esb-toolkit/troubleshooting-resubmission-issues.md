---
title: 再送信の問題のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b60ad45-d793-4de6-b9bc-3e8ef34f2b61
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1a143924b97117a708caea3006f74db6e029ca4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295098"
---
# <a name="troubleshooting-resubmission-issues"></a><span data-ttu-id="aa604-102">再送信の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa604-102">Troubleshooting Resubmission Issues</span></span>
<span data-ttu-id="aa604-103">メッセージを再送信に問題がある場合は、次を確認します。</span><span class="sxs-lookup"><span data-stu-id="aa604-103">If you have problems resubmitting messages, check the following:</span></span>  
  
-   <span data-ttu-id="aa604-104">受信場所をブラウザーからアクセスできますか。</span><span class="sxs-lookup"><span data-stu-id="aa604-104">Can you access the receive location through your browser?</span></span> <span data-ttu-id="aa604-105">WCF 入り口または SOAP の上のランプ再送信しようとする場合、フォーム http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc または http://localhost/ESB.OnRampServices/ProcessItinerary.asmx の URL を引き起こすことがあります。</span><span class="sxs-lookup"><span data-stu-id="aa604-105">If you are trying to resubmit to the WCF on-ramp or the SOAP on-ramp, the URL should be of the form http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc or http://localhost/ESB.OnRampServices/ProcessItinerary.asmx.</span></span> <span data-ttu-id="aa604-106">HTTP の受信場所に再送信しようとする場合を決定するかどうか、受信場所が正しく機能して、クエリ文字列にサンプル メッセージを追加して次の例で示すように、インターネット ブラウザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aa604-106">If you are trying to resubmit to an HTTP receive location, you can use your Internet browser to determine whether the receive location is functioning properly by appending a sample message to the query string, as shown in the following example.</span></span>  
  
    ```  
    http://localhost/HTTPOnRamp/BTSHttpReceive.dll?<SampleMessage>Sample Message Content</SampleMessage>  
    ```  
  
-   <span data-ttu-id="aa604-107">確認を BizTalk HTTP 受信アダプターが正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="aa604-107">Verify that the BizTalk HTTP receive adapter is properly configured.</span></span>