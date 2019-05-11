---
title: 要求-応答メッセージング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- request/response messaging, about request/response messaging
- SOAP adapters, message processing
- SOAP adapters, request/response messaging
- request/response messaging
- patterns, messages
- messages, request/response messaging
- request/response messaging, processing
- request/response messaging, SOAP adapters
- messages, patterns
ms.assetid: 1a2f79b5-1f44-4191-8ce1-b3c9043be4f4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38652fdb7b1b5484c4c01510416489c4437b629e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398887"
---
# <a name="request-response-messaging"></a>要求-応答メッセージング
要求/応答メッセージング パターンでは、1 つのパーティは、要求メッセージを送信および受信側パーティは、応答メッセージを返します。 要求/応答の処理の 2 つの一般的な例は、HTTP アダプター、および簡易オブジェクト アクセス プロトコル (SOAP) アダプターを使用して Web サービスの処理を使用して Web サーバーとブラウザーのある操作です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求と応答メッセージの両方が、標準的なパブリッシュ/サブスクライブ形式で処理されます。 これは、個々 のメッセージを低待機時間を必要とする 1 つとは異なる高スループットを必要とするシステムを構成する場合がありますとパフォーマンス調整を行う、BizTalk アプリケーションを理解する重要な考慮事項です。  
  
 ![要求&#47;応答メッセージング](../core/media/arch-request-response-1.gif "arch_request-応答-1")  
  
 メッセージが受信したときに要求/応答スタイルでは、受信アダプター、BizTalk Server がメッセージ ボックス データベースに最初に要求メッセージを発行します。 次にこのメッセージは、受信ポートにバインドされたオーケストレーションの可能性が、適切なサブスクライバーによって受信されます。 このサブスクライバーは、応答メッセージを作成し、要求が元の受信ポートに送信するようにするプロパティと一緒にメッセージ ボックス データベースに公開します。 最後に、応答メッセージは要求を送信し、呼び出し元アプリケーションに返される受信アダプターは、要求の発行元によってピックアップられます。 次の図は、次の手順の詳細なグラフィック表示を提供します。  
  
 ![要求&#47;SOAP アダプターで受信した応答メッセージ](../core/media/arch-request-response-2.gif "arch_request-応答-2")  
  
 **SOAP アダプターで受信した要求/応答メッセージのフロー**  
  
1. SOAP アダプターでは、エンドポイント マネージャーにメッセージを送信します。  
  
2. エンドポイント マネージャーは、メッセージ ボックスに、メッセージを公開します。  
  
3. これは、受信ポートにバインドされ、メッセージのサブスクリプション、オーケストレーションはメッセージを受信し、処理します。  
  
4. オーケストレーションでは、メッセージ ボックスに公開されている応答メッセージを送信します。  
  
5. エンドポイント マネージャーは、応答メッセージを受信します。  
  
6. エンドポイント マネージャーには、SOAP アダプターに応答が返されます。  
  
   内部の実装が認識されない場合は、この種類のパフォーマンスの動作の影響を見落とす可能性があります。 BizTalk Server は最初に、高スループットのシナリオに合わせて調整しますが、低いスループットで環境と短い待機時間、特に要求/応答シナリオでの必要性を構成することもできます。 このシナリオでチューニングするためのいくつかのコンポーネントを考慮する必要があります。 最初に、サブスクライバーについて公開されたメッセージ、ポーリング メカニズムを使用します。 ポーリング間隔の設定が高すぎる場合する可能性が要求/応答形式の対話処理を待機するよりも時間があります。  
  
   このシナリオであることを格納する 2 つのサブスクリプションに注意してください。 最初のメッセージのサブスクリプションと、1 つの応答メッセージ、およびこれにはこのポーリング間隔の影響が大きくなります。 次に、受信アダプターがさまざまなサイズのバッチでメッセージ ボックス データベースにメッセージを挿入するように構成されます。 ほとんどのアダプターには、BizTalk Server またはレジストリで、一般的なアダプター構成インターフェイス、またはパラメーターを通じてバッチ サイズを構成することが有効にします。 バッチ サイズの設定が高すぎると、個々 のメッセージ待機時間を増やすことができます。 パフォーマンス特性の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[パフォーマンス維持の計画](../core/planning-for-sustained-performance.md)します。  
  
## <a name="see-also"></a>参照  
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)