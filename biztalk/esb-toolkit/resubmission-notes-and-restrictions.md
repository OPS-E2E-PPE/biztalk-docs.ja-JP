---
title: 再送信の注意事項と制約事項 |Microsoft ドキュメント
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
ms.openlocfilehash: d03c969dc056e251d8109ce5bc0a29c16f8ffeda
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976608"
---
# <a name="resubmission-notes-and-restrictions"></a>再送信の注意事項と制約事項
再送信プロセスには、次の注意事項と制約事項が適用されます。  
  
-   ESB WCF 入り口、SOAP (ASMX) 上のランプ、XML メッセージを再送信できますか、任意の HTTP 受信場所。  
  
-   WCF の上のランプの既定の URL は、http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc です。  
  
-   ポータルの Web.config ファイルは、WCF 入り口内のエンドポイントの詳細を定義、 **\<クライアント\>** のノード、  **\<System.ServiceModel\>** 参照してください。 既定値を次に示します。  
  
    ```  
    <endpoint  
      address="http://localhost/ESB.ItineraryServices.WCF/ProcessItinerary.svc"  
      binding="wsHttpBinding"  
      bindingConfiguration="WSHttpBinding_ITwoWayAsyncVoid"  
      contract="ProcessRequest"   
      name="WSHttpBinding_ITwoWayAsyncVoid">                  
    </endpoint>  
    ```  
  
-   リモート サーバー上のランプで WCF が存在する場合、正しいサーバーをポイントするアドレスを更新する必要があります。  
  
-   ランプで SOAP (ASMX) の既定の URL は、http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx です。  
  
-   ポータルの Web.config ファイルでランプでに SOAP (ASMX) の構成を定義する、  **\<applicationSettings\>** セクションです。 既定値を次に示します。  
  
    ```  
    <setting   
      name="Microsoft_Practices_ESB_Portal_ProcessItinerary_Process"  
      serializeAs="String">  
      <value>  
        http://localhost/ESB.ItineraryServices/ProcessItinerary.asmx  
      </value>  
    </setting>  
    ```  
  
-   ASMX 入り口がリモート サーバー上にある場合は、適切なサーバー アドレスを持つ URL を更新する必要があります。  
  
-   フラット ファイルを再送信することができます、HTTP のみに書式設定されたメッセージの受信場所。 WCF または SOAP 入り口に送信することはできません。 確認する必要がありますを消費したり、フラット ファイルを解析する適切なパイプライン、HTTP 受信場所であることができます。  
  
-   再送信されたメッセージは、元のメッセージのコンテキスト プロパティのいずれか。  
  
-   再送信がメッセージ本文のみに適用されます。メッセージ全体には適用されません。  
  
-   再送信プロセスでは、1 部構成のメッセージのみをサポートします。 マルチパート メッセージを再送信プロセスを使用することはできません。  
  
-   バイナリ形式のメッセージを再送信することはできません。