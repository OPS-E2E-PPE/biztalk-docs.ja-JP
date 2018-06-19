---
title: MQSeries アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, about MQSeries adapters
- MQSeries adapters
ms.assetid: fd3dfa9a-344a-46e5-a342-bc56da7c1c50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f72d0012050fc8022b53120377aeb648641d21f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289466"
---
# <a name="what-is-the-mqseries-adapter"></a>MQSeries アダプターとは何ですか。
MQSeries アダプターを使用すると、MQSeries システムに対するメッセージの送受信を Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で行うことができます。  
  
 このアダプターは、MQSeries Server for Windows に依存しています。 MQSeries Server for Windows が Microsoft 分散トランザクション コーディネーター (MSDTC) をサポートしているため、この依存関係によって信頼性の高いメッセージングが保証されます。  
  
 アダプターでは、クラスター化された MQSeries Server、クラスター化された MQSeries キュー マネージャーに加え、クラスター化された BizTalk Server もサポートされます。  
  
 MQSeries アダプターでは、次の操作を実行できます。  
  
-   メッセージを、BizTalk Server から MQSeries のリモート定義のキュー、ローカル キュー、転送キュー、およびエイリアス キューに送信します。  
  
-   MQSeries の転送キュー、ローカル キュー、およびエイリアス キューからメッセージを受信します。  
  
-   MQSeries Server for Windows からのメッセージを送受信します (MQSeries Server は、BizTalk Server と同じコンピューターまたはリモート インストールで実行できます)。 MQSAgent (アダプターの COM+ コンポーネント) のコピーを 1 つ配置するだけで、BizTalk Server のすべてのインストールがサポートされます。  
  
-   待機間隔を指定して MQSeries Server をポーリングします。  
  
-   動的送信ポートを使用してアダプターを制御します。  
  
-   実行時にキューを動的に作成します。  
  
-   MQSeries MatchOptions に基づいてキューからメッセージを動的に受信します。  
  
-   メッセージの送信と受信のどちらも、コンテキスト プロパティをヘッダー プロパティにマップします。 MQSeries ヘッダー プロパティ (MQMD、MQXQH、MQCIH、MQIIH など) は、BizTalk Server コンテキスト プロパティを使用して取得および設定できます。  
  
-   関連付け識別子を作成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または MQSeries Server との関連付けを有効にします。  
  
-   送信メッセージの配信をおよび非トランザクション要求を送受信できます。  
  
> [!NOTE]
>  分散コンポーネント オブジェクト モデル (DCOM) によるサーバーの呼び出しを可能にする MQSeries などの機能を使用する際は、ネットワーク アドレス変換 (NAT) ベースのファイアウォールが無効になっていることを確認します。 クライアントは、実際の IP アドレスを使用してサーバーにアクセスできる必要があり、NAT ベースのファイアウォールによって、このアドレスはクライアントが認識できないように変換されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [MQSeries アダプターのコンポーネント](../core/components-of-the-mqseries-adapter.md)  
  
-   [MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md)  
  
-   [MQSeries アダプタの使用](../core/using-the-mqseries-adapter.md)  
  
-   [MQSeries アダプタのセキュリティ](../core/mqseries-adapter-security.md)