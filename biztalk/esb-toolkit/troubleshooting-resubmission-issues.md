---
title: 再送信に関する問題のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 4a095e5c0a2f6b7de9830a43fc632f9ca59aec3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399629"
---
# <a name="troubleshooting-resubmission-issues"></a><span data-ttu-id="485a6-102">再送信に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="485a6-102">Troubleshooting Resubmission Issues</span></span>
<span data-ttu-id="485a6-103">メッセージを再送信に問題がある場合は、次を確認します。</span><span class="sxs-lookup"><span data-stu-id="485a6-103">If you have problems resubmitting messages, check the following:</span></span>  
  
-   <span data-ttu-id="485a6-104">受信場所をブラウザーからアクセスできますか。</span><span class="sxs-lookup"><span data-stu-id="485a6-104">Can you access the receive location through your browser?</span></span> <span data-ttu-id="485a6-105">URL がの形式にする必要があります - ランプで WCF またはランプで SOAP を再送信しようとすると場合、 http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svcまたは http://localhost/ESB.OnRampServices/ProcessItinerary.asmxします。</span><span class="sxs-lookup"><span data-stu-id="485a6-105">If you are trying to resubmit to the WCF on-ramp or the SOAP on-ramp, the URL should be of the form http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc or http://localhost/ESB.OnRampServices/ProcessItinerary.asmx.</span></span> <span data-ttu-id="485a6-106">HTTP の受信場所に再送信しようとしている場合は、かどうか、受信場所が正しく機能して、クエリ文字列にサンプル メッセージを追加することで、次の例に示すように決定する、インターネット ブラウザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="485a6-106">If you are trying to resubmit to an HTTP receive location, you can use your Internet browser to determine whether the receive location is functioning properly by appending a sample message to the query string, as shown in the following example.</span></span>  
  
    ```  
    http://localhost/HTTPOnRamp/BTSHttpReceive.dll?<SampleMessage>Sample Message Content</SampleMessage>  
    ```  
  
-   <span data-ttu-id="485a6-107">確認を BizTalk HTTP 受信アダプターが正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="485a6-107">Verify that the BizTalk HTTP receive adapter is properly configured.</span></span>