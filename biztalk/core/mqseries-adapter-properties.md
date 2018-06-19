---
title: MQSeries アダプターのプロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQXQH_RemoteQName property [MQSeries adapters]
- MQMD_ReplyToQ property [MQSeries adapters]
- configuring [MQSeries adapters], properties
- MQXQH_MsgDesc_ReplyToQMgr property [MQSeries adapters]
- UserHttpHeaders property [MQSeries adapters]
- MQMD_CorrelId property [MQSeries adapters]
- MQXQH_MsgDesc_MsgId property [MQSeries adapters]
- MQXQH_MsgDesc_ReplyToQ property [MQSeries adapters]
- SubmissionHandle property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- MQMD_ReplyToQMgr property [MQSeries adapters]
- EnableChunkedEncoding property [MQSeries adapters]
- MQSeries adapters, properties
- MQXQH_MsgDesc_CorrelId property [MQSeries adapters]
- MQXQH_RemoteQMgrName property [MQSeries adapters]
- MQMD_MsgId property [MQSeries adapters]
ms.assetid: c3cfbc8c-4c9b-431e-b0b6-4c065a69ce6b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fae8cc1ed67f077b6ae12945da10c58cf0f147da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263570"
---
# <a name="mqseries-adapter-properties"></a>MQSeries アダプターのプロパティ
BizTalk オーケストレーションから MQSeries ヘッダー プロパティにアクセスするには、プロジェクトに MQSeries.dll アセンブリへの参照を追加する必要があります。 このアセンブリは、MQSeries アダプターをインストールした場所 ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] など) にあります。  
  
 MQSeries プロパティ スキーマを参照すると、追加のコンテキスト プロパティはさまざまな BizTalk Server 開発ツールを使用 (たとえば、**メッセージの割り当て**図形をオーケストレーション デザイナーで)。  
  
> [!NOTE]
>  MQSeries ヘッダー プロパティを使用する場合は、IBM WebSphere MQ のドキュメントに記載されているガイドラインに従うようにしてください。  
  
 アダプタでは、一部の MQSeries プロパティを自動的に昇格させます。 アプリケーションやカスタム コンポーネントでは、このように昇格されたプロパティを降格しないようにする必要があります。 また、カスタム パイプライン コンポーネントを使用して、追加のプロパティを昇格させることができます。 自動的に昇格されるプロパティは、次のとおりです。  
  
-   **BizTalk_CorrelationID**  
  
-   **MQMD_CorrelId**  
  
-   **MQMD_MsgId**  
  
-   **MQMD_ReplyToQ**  
  
-   **MQMD_ReplyToQMgr**  
  
-   **MQXQH_RemoteQMgrName**  
  
-   **MQXQH_RemoteQName**  
  
-   **MQXQH_MsgDesc_CorrelId**  
  
-   **MQXQH_MsgDesc_MsgId**  
  
-   **MQXQH_MsgDesc_ReplyToQ**  
  
-   **MQXQH_MsgDesc_ReplyToQMgr**  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プロパティのデータ型の変換](../core/data-type-conversion-of-properties.md)  
  
-   [BizTalk Server に関連するプロパティ](../core/properties-related-to-biztalk-server.md)  
  
-   [MQSeries コンテキスト プロパティ](../core/mqseries-context-properties.md)  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターの構成](../core/configuring-the-mqseries-adapter.md)