---
title: 要求-応答のメッセージング |Microsoft ドキュメント
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
ms.openlocfilehash: cd612d5f41e4648625a2a28398f20ecf74e0a4e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268522"
---
# <a name="request-response-messaging"></a>要求-応答のメッセージング
要求/応答メッセージ方式では、送信側が要求メッセージを送信し、受信側が応答メッセージを返します。 要求/応答処理の一般的な使用例としては、HTTP アダプターを使用した Web サーバーとブラウザー間の対話処理、および、Simple Object Access Protocol (SOAP) アダプターを使用した Web サービス処理の 2 つがあります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の要求/応答メッセージは、通常のパブリッシュ/サブスクライブ形式で処理されます。 このことは、BizTalk アプリケーションのパフォーマンス調整を行うときの重要な注意事項です。高いスループットを必要とするシステムは、個々のメッセージの待ち時間を短くする必要のあるシステムとは異なる構成が行われる可能性があるためです。  
  
 ![要求である (、&) #47 です。応答のメッセージング](../core/media/arch-request-response-1.gif "arch_request-応答-1")  
  
 要求/応答形式の受信アダプターでメッセージを受信する場合、BizTalk Server は、最初に要求メッセージをメッセージ ボックス データベースに公開します。 次に、適切なサブスクライバー (受信ポートにバインドされているオーケストレーションの可能性が高い) がこのメッセージを受信します。 このサブスクライバーは、応答メッセージを作成し、要求元の受信ポートに応答メッセージを返信するプロパティと一緒にメッセージ ボックス データベースに応答メッセージを公開します。 最後に、要求元のパブリッシャー (要求を送信した受信アダプター) が応答メッセージを受け取ってから、呼び出し元のアプリケーションに応答メッセージが返されます。 次の図は、これらの手順の詳細を示しています。  
  
 ![要求 (&) #47; SOAP アダプターで受信した応答メッセージ](../core/media/arch-request-response-2.gif "arch_request-応答-2")  
  
 **SOAP アダプターで受信した要求/応答メッセージのフロー**  
  
1.  SOAP アダプターは、メッセージをエンドポイント マネージャーに送信します。  
  
2.  エンドポイント マネージャーは、メッセージをメッセージ ボックス データベースに公開します。  
  
3.  受信ポートにバインドされている (メッセージにサブスクリプションを含む) オーケストレーションは、メッセージを受信して処理します。  
  
4.  オーケストレーションは、メッセージ ボックス データベースに公開されている応答メッセージを送信します。  
  
5.  エンドポイント マネージャーは、応答メッセージを受け取ります。  
  
6.  エンドポイント マネージャーは、応答を SOAP アダプターに返します。  
  
 内部の実装を理解していない場合、パフォーマンスに対するこのような動作の影響は見過ごされがちです。 BizTalk Server は、当初は、高スループット シナリオ用にチューニングされていますが、低いスループットや少ない待機時間 (特に要求/応答シナリオ) に合わせた環境の構成も行うことができます。 このシナリオに合わせて、いくつかのコンポーネントを考慮する必要があります。 最初に、サブスクライバーは、ポーリング機構を通じて公開されたメッセージを取得します。 ポーリング間隔が大きすぎると、要求/応答形式の対話処理の待機時間が長くなる可能性があります。  
  
 このシナリオでは 2 つのサブスクリプション (最初のメッセージのサブスクリプションと応答メッセージのサブスクリプション) を使用していることに注意してください。これにより、このポーリング間隔の影響が大きくなります。 次に、受信アダプターを構成して、さまざまなサイズのバッチ単位で、メッセージ ボックス データベースにメッセージを挿入します。 ほとんどのアダプターでは、通常のアダプター構成インターフェイス、BizTalk Server のパラメーター、またはレジストリを使用して、バッチ サイズを構成できます。 バッチ サイズが大きすぎると、個々のメッセージの待機時間が長くなる可能性があります。 パフォーマンス特性の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[継続的なパフォーマンスの計画](../core/planning-for-sustained-performance.md)です。  
  
## <a name="see-also"></a>参照  
 [ランタイム アーキテクチャ](../core/runtime-architecture.md)