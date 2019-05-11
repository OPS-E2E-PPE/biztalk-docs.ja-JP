---
title: ランタイムのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- architecture, runtime
- runtime
ms.assetid: feff9a84-f19b-44c9-8d05-8e6015bb1ef9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b6b7a01f8919a1c2bee415df3733394462d59f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393973"
---
# <a name="runtime-architecture"></a>ランタイム アーキテクチャ
さまざまなコンポーネントに関する情報を確認する前に詳細[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントが、製品の全体的なアーキテクチャに適合させる方法を理解することが重要になります。 BizTalk Server ランタイムは、メッセージが、システムに公開および 1 つまたは複数のアクティブなサブスクライバーで受信し、パブリッシュ/サブスクライブ アーキテクチャに基づいて構築されます。 このアーキテクチャのさまざまな種類があります。 しかし、BizTalk Server で実装されるモデルとも呼ばれます*コンテンツに基づく公開/定期受信*します。  
  
 コンテンツ ベースのパブリッシュ/サブスクライブ モデルでは、サブスクライバーは、メッセージに関する条件のセットを使用して受信するメッセージを指定します。 メッセージが発行時に評価され、すべてのアクティブなサブスクライバー (フィルター式によって示されます) のサブスクリプションに一致するメッセージが表示されます。 BizTalk Server に適用される、コンテンツに基づくが、若干不適切な名称、ただし、サブスクリプションを構築するための条件は、メッセージの内容から取得する必要はなくもメッセージに関するコンテキスト情報を含めることができますです。 サブスクリプション メカニズムの詳細については、次を参照してください。[発行およびサブスクライブ アーキテクチャ](../core/publish-and-subscribe-architecture.md)します。  
  
 次のセクションでは、BizTalk Server ランタイム アーキテクチャのさまざまなコンポーネントについて説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server メッセージ](../core/the-biztalk-server-message.md)  
  
-   [メッセージのライフサイクル](../core/lifecycle-of-a-message.md)  
  
-   [メッセージの処理](../core/processing-the-message.md)  
  
-   [要求 - 応答メッセージング](../core/request-response-messaging.md)  
  
-   [メッセージング エンジン](../core/the-messaging-engine.md)  
  
-   [エンティティ](../core/entities.md)  
  
-   [アイテム](../core/artifacts.md)  
  
-   [Enterprise Single Sign-On (SSO)](../core/enterprise-single-sign-on-sso.md)  
  
-   [ビジネス ルール エンジン](../core/business-rules-engine.md)  
  
-   [BizTalk アセンブリ](../core/biztalk-assemblies.md)