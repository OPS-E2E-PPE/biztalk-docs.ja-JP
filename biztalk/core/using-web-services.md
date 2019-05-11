---
title: Web サービスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24af6961e888f8cda21e8d280451382160e2b5af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262114"
---
# <a name="using-web-services"></a>Web サービスの使用
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービスの組み込みサポートを提供します。 BizTalk Server は、再利用とすべての既存の Web サービス、オーケストレーション内で集計できます。 (公開) を公開することも、オーケストレーションを Web を分離する Web サービスとしてのサービス ロジックとビジネス プロセス ロジック。  
  
 BizTalk Server では、Web サービスのネイティブ アダプターのサポートを実装します。 ネイティブ アダプタのサポートは、スケーラビリティ、フォールト トレランス、および Web サービスの機能を 1 行のコードを記述することがなく追跡を提供します。 SOAP アダプターについては、次を参照してください。 [SOAP アダプター](../core/soap-adapter.md)します。  
  
 BizTalk Server での Web サービスのサポートが 2 つのカテゴリに分類されます。 Web サービスの使用または Web サービスを呼び出すと公開または作成します。  
  
 利用または Web サービスを発行する前に、asp.net XML Web サービスの理解が必要です。 XML Web サービスの基本についてにある「XML Web サービスの基本事項」の記事を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057)します。  
  
 **Web サービスの使用**  
  
 オーケストレーション内から (呼び出し) Web サービスを使用することができます。 複数の Web サービスは、ビジネス プロセス全体を完了する 1 つのオーケストレーションに集計できます。  
  
 **Web サービスの公開**  
  
 BizTalk Web サービス公開ウィザードを使用して Web サービスを発行することができます。 オーケストレーションや送信アダプターは、これらの公開済み Web サービスを使用できます。  
  
 **SOAP ヘッダーの使用**  
  
 BizTalk Server では、定義されていると、不明な SOAP ヘッダーのサポートを提供します。 BizTalk Server では、Web サービスで定義されている各 SOAP ヘッダー コンテキスト プロパティを作成します。  
  
 **Web サービス標準**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送受信するときに任意の Web サービス標準を使用する必要があります。 すべての標準がテストされています。 通常、WCF によってサポートされる標準でサポートされても[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 サンプルの標準は次のとおりです。  
  
-   WS-ReliableMessaging  
  
-   WS-Security  
  
-   Ws-secureconversation  
  
-   Ws-trust  
  
-   WS フェデレーション  
  
-   WS-Addressing  
  
-   Ws-policy  
  
-   WS-MetadataExchange  
  
-   Ws-coordination  
  
-   Ws-atomic  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Web サービスの利用](../core/consuming-web-services.md)  
  
-   [Web サービスの公開](../core/publishing-web-services.md)  
  
-   [SOAP ヘッダーの使用](../core/using-soap-headers.md)