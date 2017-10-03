---
title: "メッセージ コンテキスト プロパティを BizTalk Server で |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties, accessing
- message context properties, BizTalk Server
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e92e458ec6927ab8e1bc6082cd9a71ee3e4387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-context-properties-in-biztalk-server"></a>BizTalk Server におけるメッセージのコンテキスト プロパティ
BizTalk Server オーケストレーションから TIBCO Enterprise Message System のメッセージ記述子フィールドにアクセスするへの参照を追加する必要があります**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**をプロジェクトにします。 このアセンブリにある **\<TIBCO EMS_Adapter_installation_directory > \bin**です。 この TIBCO EMS のプロパティ スキーマにアクセスすると、さらに多くのコンテキスト プロパティに、さまざまな BizTalk Server 開発ツールからアクセスできるようになります (オーケストレーション デザイナのメッセージ割り当て図形など)。  
  
## <a name="accessing-context-properties"></a>コンテキスト プロパティへのアクセス  
 コンテキスト プロパティにアクセスするには、TIBCO EMS 名前空間の使用できるプロパティのうちいずれかを指定します。 TIBCO EMS 用の BizTalk アダプタにバインドされたポートから受信したメッセージのコンテキスト プロパティを読み取るには、式の中で次の構文を使用します。  
  
```  
Message(TibcoEMS.Property)  
```  
  
 詳細については、次を参照してください。 [TIBCO Enterprise Message Service メッセージ記述子プロパティ](../core/tibco-enterprise-message-service-message-descriptor-properties.md)です。  
  
 BizTalk Server では、メッセージを変更できません。 このため、メッセージのコンテキスト プロパティに値を割り当てるには、新しいメッセージを作成し、メッセージのコンテキストを設定して (既存のメッセージを割り当てるなど)、必要なプロパティを設定します。  
  
 TIBCO EMS の BizTalk アダプターにバインドされている送信ポートに送信メッセージに TIBCO EMS のコンテキスト プロパティを割り当てる、メッセージ代入演算子を使用し、TIBCO EMS 名前空間に使用できるコンテキスト プロパティのいずれかを指定します。 構文は次のとおりです。  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="see-also"></a>参照  
 [メッセージ コンテキスト プロパティ](../core/message-context-properties2.md)