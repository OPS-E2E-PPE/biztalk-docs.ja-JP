---
title: 再送信の注意事項と制約事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 391064a9-1d61-4b10-97ab-d93b37d1ae23
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f08f6a2740331518d6fc92fb0c12e6f89d1b79f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401504"
---
# <a name="resubmission-notes-and-restrictions"></a>再送信の注意事項と制約事項
再送信プロセスには、次の注意事項と制限が適用されます。  
  
-   ESB WCF ランプで、SOAP (ASMX) 上のランプ、XML メッセージを再送信できますか、任意の HTTP 受信場所。  
  
-   ランプで WCF の既定の URL は http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svcします。  
  
-   ポータルの Web.config ファイルでランプでに WCF のエンドポイントの詳細を定義する、 **\<クライアント\>** のノード、 **\<System.ServiceModel\>** セクション。 既定値は、次のとおりです。  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   リモート サーバー上のランプで WCF が存在する場合は、正しいサーバーをポイントするアドレスを更新する必要があります。  
  
-   ランプで SOAP (ASMX) の既定の URL は http://localhost/ESB.ItineraryServices/ProcessItinerary.asmxします。  
  
-   ポータルの Web.config ファイルでランプでに SOAP (ASMX) の構成を定義する、 **\<applicationSettings\>** セクション。 既定値は、次のとおりです。  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   ASMX の上のランプがリモート サーバー上にある場合は、適切なサーバー アドレスの URL を更新する必要があります。  
  
-   フラット ファイルを再送信することができますのみ HTTP を書式設定されたメッセージの受信場所。 WCF または SOAP に着手するには、それらを送信できません。 確認する必要があります消費やフラット ファイルを解析できますを適切なパイプラインには、HTTP 受信場所であること。  
  
-   再送信されたメッセージは、元のメッセージのコンテキスト プロパティのいずれかありません。  
  
-   再送信がメッセージ本文のみに適用されます。メッセージ全体には適用されません。  
  
-   再送信プロセスでは、1 つの部分のメッセージのみをサポートします。 マルチパート メッセージを再送信プロセスを使用することはできません。  
  
-   バイナリ形式のメッセージを再送信することはできません。