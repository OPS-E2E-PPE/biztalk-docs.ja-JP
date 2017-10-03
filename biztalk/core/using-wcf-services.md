---
title: "WCF サービスの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29b984bcda798796565113739c6088af6d569f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-wcf-services"></a>WCF サービスの使用
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Communication Foundation (WCF) の組み込みサポートを提供します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用すると、再利用し、すべての既存の WCF サービス、オーケストレーション内に集約できます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF サービスでのネイティブ アダプタのサポートも実装します。 ネイティブ アダプタのサポートにより、コードを記述しなくても、WCF サービスのスケーラビリティ、フォールト トレランス、および追跡の機能を利用できます。 WCF アダプターについては、次を参照してください。 [WCF アダプタ](../core/wcf-adapters.md)です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での WCF サービスのサポートは、WCF サービスの公開 (作成) と WCF サービスの呼び出し (利用) の 2 種類に分類されます。  
  
 **WCF サービスの公開**  
  
 WCF アダプタを使用してオーケストレーションとスキーマを Web サービスとして公開すると、WCF サービス ロジックとビジネス プロセス ロジックを区別できます。 分離 WCF アダプタでは、BizTalk WCF サービス公開ウィザードを使用して、インターネット インフォメーション サービス (IIS) で実行されている Web アプリケーションでホストされる分離された WCF 受信場所を作成できます。 インプロセス WCF アダプタでは、BizTalk WCF サービス公開ウィザードを使用して、WCF に関する場所のサービス メタデータを公開できます。  メタデータの公開によって、svcutil.exe ユーティリティを使用してクライアント コードを作成できるようになります。  
  
 **WCF サービスの使用**  
  
 BizTalk WCF サービス使用ウィザードを使用すると、BizTalk オーケストレーションや種類など、WCF サービスのメタデータ ドキュメントに基づいて WCF サービスを利用するための BizTalk アイテムを生成できます。 メタデータによって、送信ポートはクライアントとして外部サービスにアクセスできます。 メタデータは、エンドポイント アドレス、バインド、およびコントラクトの記述にのみ使用されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF サービスの公開](../core/publishing-wcf-services.md)  
  
-   [WCF サービスの使用](../core/consuming-wcf-services.md)  
  
-   [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [WCF アダプターのチュートリアル](../core/wcf-adapter-walkthroughs.md)