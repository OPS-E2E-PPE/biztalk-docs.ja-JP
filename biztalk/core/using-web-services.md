---
title: "Web サービスの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services
- Web services, about Web services
- orchestrations, Web services
- Web services, orchestrations
ms.assetid: a54261e3-d8ef-4770-8d9a-147685846051
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236acb42c010effe5c3d45cde1daaf9a7097ede5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-web-services"></a>Web サービスの使用
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、Web サービスの組み込みサポートが提供されています。 BizTalk Server は、既存のすべての Web サービスを再利用し、オーケストレーション内に集約できます。 また、オーケストレーションを Web サービスとして公開し、Web サービス ロジックとビジネス プロセス ロジックを区別することもできます。  
  
 BizTalk Server は、Web サービスのネイティブ アダプタのサポートを実装しています。 ネイティブ アダプタのサポートにより、コードを記述しなくても、Web サービスのスケーラビリティ、フォールト トレランス、および追跡の機能を利用できます。 SOAP アダプタについては、次を参照してください。 [SOAP アダプター](../core/soap-adapter.md)です。  
  
 BizTalk Server での Web サービスのサポートは、Web サービスの使用または呼び出しと、Web サービスの公開または作成の 2 つのカテゴリに分類されます。  
  
 Web サービスを利用または公開する前に、ASP.NET の XML Web サービスについて理解しておく必要があります。 XML Web サービスの基本についての説明についてにある「XML Web サービスの基本事項」の記事を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=193057](http://go.microsoft.com/fwlink/?LinkId=193057)です。  
  
 **Web サービスの使用**  
  
 Web サービスは、オーケストレーション内から利用 (呼び出し) できます。 複数の Web サービスを 1 つのオーケストレーションに集約して、ビジネス プロセス全体を完了できます。  
  
 **Web サービスの公開**  
  
 BizTalk Web サービス公開ウィザードを使用して、Web サービスを公開できます。 オーケストレーションおよび送信アダプタでは、これらの公開された Web サービスを使用できます。  
  
 **SOAP ヘッダーの使用**  
  
 BizTalk Server では、定義済みの SOAP ヘッダーと不明な SOAP ヘッダーがサポートされています。 定義済みの各 SOAP ヘッダーのコンテキスト プロパティが BizTalk Server によって Web サービス内に作成されます。  
  
 **Web サービス標準**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送受信の際に任意の Web サービス標準に対応して動作します。 すべての標準がテストされているわけではありません。 一般的に、WCF によってサポートされる標準は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でもサポートされます。 サポートされる標準には、次のものがあります。  
  
-   WS-ReliableMessaging  
  
-   WS-Security  
  
-   WS-SecureConversation  
  
-   WS-Trust  
  
-   WS-Federation  
  
-   WS-Addressing  
  
-   WS-Policy  
  
-   WS-MetadataExchange  
  
-   WS-Coordination  
  
-   WS-Atomic  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Web サービスの使用](../core/consuming-web-services.md)  
  
-   [Web サービスの公開](../core/publishing-web-services.md)  
  
-   [SOAP ヘッダーの使用](../core/using-soap-headers.md)