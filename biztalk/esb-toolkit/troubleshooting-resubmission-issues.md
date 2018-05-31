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
# <a name="troubleshooting-resubmission-issues"></a>再送信の問題のトラブルシューティング
メッセージを再送信に問題がある場合は、次を確認します。  
  
-   受信場所をブラウザーからアクセスできますか。 WCF 入り口または SOAP の上のランプ再送信しようとする場合、フォーム http://localhost/ESB.OnRampServices.WCF/ProcessItinerary.svc または http://localhost/ESB.OnRampServices/ProcessItinerary.asmx の URL を引き起こすことがあります。 HTTP の受信場所に再送信しようとする場合を決定するかどうか、受信場所が正しく機能して、クエリ文字列にサンプル メッセージを追加して次の例で示すように、インターネット ブラウザーを使用できます。  
  
    ```  
    http://localhost/HTTPOnRamp/BTSHttpReceive.dll?<SampleMessage>Sample Message Content</SampleMessage>  
    ```  
  
-   確認を BizTalk HTTP 受信アダプターが正しく構成されています。