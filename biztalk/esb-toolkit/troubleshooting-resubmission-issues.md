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
# <a name="troubleshooting-resubmission-issues"></a>再送信に関する問題のトラブルシューティング
メッセージを再送信に問題がある場合は、次を確認します。  
  
-   受信場所をブラウザーからアクセスできますか。 URL がの形式にする必要があります - ランプで WCF またはランプで SOAP を再送信しようとすると場合、 http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svcまたは http://localhost/ESB.OnRampServices/ProcessItinerary.asmxします。 HTTP の受信場所に再送信しようとしている場合は、かどうか、受信場所が正しく機能して、クエリ文字列にサンプル メッセージを追加することで、次の例に示すように決定する、インターネット ブラウザーを使用できます。  
  
    ```  
    http://localhost/HTTPOnRamp/BTSHttpReceive.dll?<SampleMessage>Sample Message Content</SampleMessage>  
    ```  
  
-   確認を BizTalk HTTP 受信アダプターが正しく構成されています。