---
title: ランタイム アーキテクチャ |Microsoft ドキュメント
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
ms.openlocfilehash: 9e45ac745dbf6704f06f61155b3f57edfdec9e09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268994"
---
# <a name="runtime-architecture"></a>ランタイム アーキテクチャ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のさまざまなコンポーネントに関する詳細な情報を確認する前に、コンポーネントが製品の全体的なアーキテクチャにどのように組み込まれているかを理解しておくことが重要です。 BizTalk Server ランタイムは、メッセージがシステムに公開され、次に 1 つまたは複数のアクティブなサブスクライバーによって受信される公開/サブスクライブ アーキテクチャに基づいて構築されています。 このアーキテクチャの異なる特性がありますが、BizTalk Server で実装されるモデルとも呼ばれます*コンテンツ ベースのパブリッシュ/サブスクライブ*です。  
  
 コンテンツ ベースの公開/サブスクライブ モデルでは、サブスクライバーはメッセージに関する条件のセットを使用して、受信するメッセージを指定します。 メッセージは公開されたときに評価され、サブスクリプションに一致するすべてのアクティブなサブスクライバー (フィルター式で示す) がメッセージを受信します。 BizTalk Server では、サブスクリプションを構築するために使用する条件がメッセージの内容から取得される必要がなく、メッセージに関するコンテキスト情報も含まれる場合があるので、コンテンツ ベースという名前はあまりふさわしくありません。 サブスクリプション メカニズムの詳細については、「[パブリッシュとサブスクライブ アーキテクチャ](../core/publish-and-subscribe-architecture.md)です。  
  
 次のセクションでは、BizTalk Server ランタイム アーキテクチャのさまざまなコンポーネントについて説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server メッセージ](../core/the-biztalk-server-message.md)  
  
-   [メッセージのライフ サイクル](../core/lifecycle-of-a-message.md)  
  
-   [メッセージの処理](../core/processing-the-message.md)  
  
-   [要求-応答のメッセージング](../core/request-response-messaging.md)  
  
-   [メッセージング エンジン](../core/the-messaging-engine.md)  
  
-   [エンティティ](../core/entities.md)  
  
-   [成果物](../core/artifacts.md)  
  
-   [エンタープライズ シングル サインオン (SSO)](../core/enterprise-single-sign-on-sso.md)  
  
-   [ビジネス ルール エンジン](../core/business-rules-engine.md)  
  
-   [BizTalk アセンブリ](../core/biztalk-assemblies.md)