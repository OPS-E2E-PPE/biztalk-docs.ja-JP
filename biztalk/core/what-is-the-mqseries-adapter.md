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
ms.openlocfilehash: 10157d2e29b9ab3b23f1f938cdc55a2c1b7d7f5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243059"
---
# <a name="what-is-the-mqseries-adapter"></a>MQSeries アダプターとは何ですか。
MQSeries アダプターの送信し、Microsoft を使用して MQSeries システムに対するメッセージを受信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
 アダプターは、Windows の MQSeries サーバーに依存します。 この設計は、信頼性の高い MQSeries Server for Windows が Microsoft 分散トランザクション コーディネーター (MSDTC) をサポートするためのメッセージングが保証されます。  
  
 アダプターには、クラスター化された MQSeries サーバーとクラスター化された MQSeries キュー マネージャー、およびクラスター化された BizTalk サーバーがサポートしています。  
  
 MQSeries アダプターを使用して、次を行うことができます。  
  
- BizTalk Server から MQSeries のリモート定義のキュー、ローカル キュー、転送キュー、およびエイリアス キューにメッセージを送信します。  
  
- MQSeries 転送キュー、ローカル キュー、およびエイリアス キューからメッセージを受信します。  
  
- Windows 用の MQSeries Server からメッセージを送受信 (BizTalk Server と同じコンピューターまたはリモート インストール、MQSeries Server を実行できます)。 のみ、BizTalk Server のすべてのインストールをサポートするために MQSAgent (COM + コンポーネントのアダプター) の 1 つのコピーを展開する必要があるとします。  
  
- 待機間隔と MQSeries Server をポーリングします。  
  
- アダプターを制御するポートを使用して動的に送信します。  
  
- 実行時にキューを動的に作成します。  
  
- MQSeries matchoptions に基づいてキューからメッセージを動的に受信します。  
  
- ヘッダーのプロパティの両方の送信とメッセージを受信するには、コンテキスト プロパティをマップします。 取得し、コンテキスト プロパティを BizTalk Server から MQSeries ヘッダーのプロパティ (MQMD、MQXQH、MQCIH、MQIIH など) を設定できます。  
  
- いずれかとの相関関係を有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または MQSeries Server の関連付け識別子を作成します。  
  
- 送信メッセージのトランザクションおよび非トランザクション配信を要求して受信します。  
  
> [!NOTE]
>  分散コンポーネント オブジェクト モデル (DCOM) によるサーバーの呼び出しを可能にする MQSeries などの機能を使用する際は、ネットワーク アドレス変換 (NAT) ベースのファイアウォールが無効になっていることを確認します。 クライアントは、実際の IP アドレスを使用してサーバーにアクセスできる必要があり、NAT ベースのファイアウォールによって、このアドレスはクライアントが認識できないように変換されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [MQSeries アダプターのコンポーネント](../core/components-of-the-mqseries-adapter.md)  
  
-   [MQSeries アダプターのアーキテクチャ](../core/mqseries-adapter-architecture.md)  
  
-   [MQSeries アダプターの使用](../core/using-the-mqseries-adapter.md)  
  
-   [MQSeries アダプターのセキュリティ](../core/mqseries-adapter-security.md)