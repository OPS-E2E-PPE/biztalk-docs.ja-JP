---
title: "WCF アダプター FAQ: サービス アーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bad0063-ccff-41f4-b4e0-a02b49403c2d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b73b70474fd30e3a571f59558d6dc439cb981f64
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapter-faq-service-architecture"></a>WCF アダプター FAQ: サービスのアーキテクチャ
## <a name="what-is-the-difference-between-a-wcf-custom-behavior-and-a-biztalk-pipeline-component"></a>WCF カスタム動作と BizTalk パイプライン コンポーネントの違い  
 一見したところ、WCF カスタム動作は従来の BizTalk パイプラインとよく似ています。 どちらもメッセージのインターセプションという基本概念を活用して、送信先へのメッセージのフローに割り込み、カスタム メッセージ処理を実行し、そのメッセージを送信先に転送します。 このインターセプションは、メッセージが BizTalk Server により処理される前 (受信場所にバインド) または後 (送信ポートにバインド) に行うことができます。 2 つの方法内でこのインターセプションがどのように行われるかについては、実装の点だけでなく、インターセプションの時点でも違いがあります。 次のような違いがあります。  
  
-   パイプラインはオーケストレーションにより使用できます。 WCF 動作は BizTalk Server 内の WCF アダプターによる呼び出しに制限されます。  
  
-   パイプラインは BizTalk Server に固有の古い技術です。 WCF 動作は BizTalk Server で使用でき、他の純粋な WCF シナリオでも使用できます。  
  
-   パイプラインのデコード、検証などの設定パイプライン ステージ内でライブします。WCF 動作は、(下記参照)、4 つのインターセプション エントリ ポイントのいずれかでメッセージ フローに接続することができます。  
  
-   パイプラインは純粋に実行時の機能です。 WCF 動作も同様ですが、BizTalk Server 管理コンソール内から構成時に設定された値に関連する制約やデータの制約を行うこともできます。  
  
-   パイプラインは、WCF 動作は、WCF メッセージに対し、BizTalk メッセージを操作できます。 つまり、パイプラインでは BizTalk コンテキスト プロパティの昇格などの処理ができ、WCF 動作では WCF メッセージ プロパティにアクセスできます。  
  
-   WCF または WCF アダプターにマルチパート メッセージのモデルはありません。 しかし、パイプライン コンポーネントでは必要な任意の方法で BizTalk メッセージを操作できるため、必要に応じてマルチパート メッセージを処理できます。  
  
## <a name="for-the-receive-locations-or-send-ports-using-the-wcf-basichttp-and-wcf-wshttp-adapters-what-type-of-encoding-should-i-select"></a>WCF-BasicHttp アダプターと WCF-WSHttp アダプターを使用する受信場所または受信ポートの場合に選択するエンコードの種類  
 どちらのアダプターにも、HTTP ベースのメッセージ エンコードとテキスト エンコードがあります。 メッセージ エンコードではメッセージに使用される SOAP エンコーダーを指定します。これは MTOM (Message Transmission Organization Mechanism) またはテキストです。 テキストを選択した場合、テキスト エンコードを選択する必要があります。 テキスト エンコードには、unicodeFFF (ビッグ エンディアン)、utf-16 (16 ビット エンコード)、および utf-8 (8 ビット エンコード) があります。  
  
 MTOM はバイナリ データの最も効率的な転送メカニズムであり、使用をお勧めします。 ただし、サービスで MTOM データを処理できることが必要になるため、テキスト形式に比べ移植性は劣ります。 MTOM は、バイナリ以外の標準的なデータの転送に使用した場合、実際にはテキスト オプションより効率が落ちることがあります。 テキストは広く普及し、プラットフォーム間の相互運用性に優れていますが、転送対象データがテキスト以外のコンテンツである場合、効率が低下します。 これが、WCF サービス コントラクトの使用時にバインディング エンコードを選択する重要な要因となります。 WCF 操作で転送し処理するデータを知ることで、メッセージ エンコードを正しく選択できるようになります。