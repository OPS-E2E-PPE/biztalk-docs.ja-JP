---
title: MQSeries アダプターのメッセージ フロー |Microsoft Docs
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
ms.openlocfilehash: 49f861b47457c0f24faf4667c9f22b93b2c8034b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013931"
---
# <a name="mqseries-adapter-message-flow"></a>MQSeries アダプターのメッセージ フロー
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピュータから発信されるメッセージは、まず、Windows 上で実行されている MQSeries Server に渡されます。 Windows 上で実行されている MQSeries Server は、BizTalk Server が実行されているコンピュータと同じコンピュータでもかまいません。 メッセージは、MQSeries Server for Windows コンピュータ経由で、UNIX などのオペレーティング システム上の MQSeries Server ホストにルーティングされます。 その後、アプリケーションは、MQSeries キューからメッセージを取得します。  

 アプリケーションから発信されるメッセージは、まず、MQSeries Server 上の MQSeries キューに格納されます。 MQSeries Server は、メッセージを MQSeries Server for Windows コンピュータに転送します。 BizTalk Server は、MQSeries Server for Windows コンピュータからメッセージを受信し、そのメッセージを適切なアプリケーションに転送します。  

 MQSeries アダプタでは、次のメッセージング シナリオをサポートします。  


|        **Scenario**        |                                                                                                                                                                                                                 **[説明]**                                                                                                                                                                                                                 |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          Receive           |                                                                                                                                           アダプタは、MQSeries Server からメッセージを受信します。受信したメッセージは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に渡されます。                                                                                                                                           |
| 送信 (静的な一方向のポート) |                                                                                                                                                      アダプタは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から発信されるメッセージをルーティングします。                                                                                                                                                      |
|        動的送信        |                                                                                                                                                                                   アプリケーションは実行時に送信先アドレス (URI) を選択できます。                                                                                                                                                                                    |
|      動的受信       |                                                                                                                             により、アプリケーションの実行時に設定して、発信元アドレス (URI) を選択、 **MQSeries.DynamicReceive**コンテキスト プロパティを**はい**動的な受信アドレスを指定するとします。                                                                                                                             |
|        Correlation         | アダプタからのメッセージは、複数の種類のメッセージを処理できるオーケストレーションの特定のインスタンスに関連付けられます。<br /><br /> MQSeries Server は送信請求 - 応答を使用して関連付け識別子を作成できます。または、BizTalk Server が関連付け識別子を作成できます。<br /><br /> 関連付けセットの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプを参照してください。 |

 パイプライン、オーケストレーション、コンテンツ ベースのルーティングでのポートおよびアダプタの使用方法の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプを参照してください。 アダプターの関連付け識別子の使用に関する詳細については、次を参照してください。[関連付けメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)します。  

 アダプターでのフィルター処理で使用できるヘッダー プロパティについては、次を参照してください。 [BizTalk Server に関連するプロパティ](../core/properties-related-to-biztalk-server.md)と[MQSeries コンテキスト プロパティ](../core/mqseries-context-properties.md)します。  

## <a name="see-also"></a>参照  
 [MQSeries アダプターの使用](../core/using-the-mqseries-adapter.md)