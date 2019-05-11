---
title: WCF サービスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services
- Windows Communication Foundation (WCF)
ms.assetid: 34fe5e4c-6a92-4627-b2aa-e8b58a708320
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81082cacafb1f04d54920648d8f588a4b2ccc50a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396733"
---
# <a name="using-wcf-services"></a>WCF サービスの使用
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Communication Foundation (WCF) 用の組み込みサポートを提供します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 再利用し、すべての既存の WCF サービス、オーケストレーション内の集計ができます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] WCF サービスにもネイティブ アダプターのサポートを実装します。 ネイティブ アダプタのサポートは、スケーラビリティ、フォールト トレランス、およびコードを記述することがなく追跡の WCF サービスの機能を提供します。 WCF アダプターについては、次を参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。  
  
 WCF サービスでのサポート[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は 2 つのカテゴリに分類されます: 発行または WCF サービスの場合は、作成または呼び出しまたは WCF サービスを使用します。  
  
 **WCF サービスの公開**  
  
 (公開) を公開するオーケストレーションおよびスキーマを WCF 分離 WCF アダプターで WCF サービスとしてのサービス ロジックとビジネス プロセス ロジック。 分離を作成する、BizTalk WCF サービス公開ウィザードを使用する分離 WCF アダプタでの WCF 受信場所では、インターネット インフォメーション サービス (IIS) を実行する Web アプリケーションによってホストされています。 インプロセス WCF アダプタでは、BizTalk WCF サービス公開ウィザードで WCF の任意の場所のサービス メタデータを発行できます。  メタデータの公開では、svcutil.exe ユーティリティを使用してクライアント コードの作成を許可します。  
  
 **WCF サービスの使用**  
  
 BizTalk WCF サービス使用ウィザードを使用して、BizTalk オーケストレーションや種類、WCF サービスのメタデータ ドキュメントに基づいて WCF サービスを使用するなどの BizTalk アイテムを生成することができます。 メタデータは、クライアントとして外部サービスにアクセスする送信ポートを使用します。 純粋に、バインド、およびコントラクト、エンドポイント アドレスを記述するメタデータが使用されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF サービスの公開](../core/publishing-wcf-services.md)  
  
-   [WCF サービスの利用](../core/consuming-wcf-services.md)  
  
-   [WCF アダプターのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [WCF アダプターのチュートリアル](../core/wcf-adapter-walkthroughs.md)