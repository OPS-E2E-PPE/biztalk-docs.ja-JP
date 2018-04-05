---
title: MQSeries アダプタのメッセージ フロー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, message flow
ms.assetid: aa5c8523-afd6-4181-9c11-a150857a7790
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5df8549f99d376ea518b160ac1505aaac7feb5fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-message-flow"></a>MQSeries アダプタのメッセージ フロー
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピュータから発信されるメッセージは、まず、Windows 上で実行されている MQSeries Server に渡されます。 Windows 上で実行されている MQSeries Server は、BizTalk Server が実行されているコンピュータと同じコンピュータでもかまいません。 メッセージは、MQSeries Server for Windows コンピュータ経由で、UNIX などのオペレーティング システム上の MQSeries Server ホストにルーティングされます。 その後、アプリケーションは、MQSeries キューからメッセージを取得します。  
  
 アプリケーションから発信されるメッセージは、まず、MQSeries Server 上の MQSeries キューに格納されます。 MQSeries Server は、メッセージを MQSeries Server for Windows コンピュータに転送します。 BizTalk Server は、MQSeries Server for Windows コンピュータからメッセージを受信し、そのメッセージを適切なアプリケーションに転送します。  
  
 MQSeries アダプタでは、次のメッセージング シナリオをサポートします。  
  
|**Scenario**|**Description**|  
|------------------|---------------------|  
|Receive|アダプタは、MQSeries Server からメッセージを受信します。受信したメッセージは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡されます。|  
|送信 (静的な一方向のポート)|アダプタは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から発信されるメッセージをルーティングします。|  
|動的送信|アプリケーションは実行時に送信先アドレス (URI) を選択できます。|  
|動的受信|により、アプリケーションを設定して、実行時に、発信元アドレス (URI) を選択、 **MQSeries.DynamicReceive**コンテキスト プロパティを**はい**と動的な受信アドレスを指定します。|  
|Correlation|アダプタからのメッセージは、複数の種類のメッセージを処理できるオーケストレーションの特定のインスタンスに関連付けられます。<br /><br /> MQSeries Server は送信請求 - 応答を使用して関連付け識別子を作成できます。または、BizTalk Server が関連付け識別子を作成できます。<br /><br /> 関連付けセットの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプを参照してください。|  
  
 パイプライン、オーケストレーション、コンテンツ ベースのルーティングでのポートおよびアダプタの使用方法の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプを参照してください。 詳細については、アダプターに関連付け識別子を使用して、次を参照してください。[を相互に関連付けるメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)です。  
  
 アダプターでのフィルタ リングに使用できるヘッダー プロパティについては、次を参照してください。[プロパティに関連する BizTalk Server](../core/properties-related-to-biztalk-server.md)と[MQSeries コンテキスト プロパティ](../core/mqseries-context-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプタの使用](../core/using-the-mqseries-adapter.md)