---
title: "TIBCO EMS メッセージ コンテキスト プロパティを使用して |Microsoft ドキュメント"
description: "BizTalk Server オーケストレーションで TIBCO Enterprise Message System のメッセージ記述子フィールドを使用します。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5433e454d161c77ac140167e9af082eaee7c2032
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="message-context-properties-in-tibco-ems"></a>TIBCO EMS メッセージ コンテキスト プロパティ

## <a name="tibcoemspropertiesdll"></a>TibcoEMSProperties.dll
BizTalk Server オーケストレーションから TIBCO Enterprise Message System のメッセージ記述子フィールドにアクセスするへの参照を追加する必要があります**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**をプロジェクトにします。 このアセンブリにある **\<TIBCO EMS_Adapter_installation_directory\>\bin**です。 この TIBCO EMS のプロパティ スキーマにアクセスすると、さらに多くのコンテキスト プロパティに、さまざまな BizTalk Server 開発ツールからアクセスできるようになります (オーケストレーション デザイナのメッセージ割り当て図形など)。  
  
## <a name="access-context-properties"></a>コンテキスト プロパティにアクセスします。  
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
  
## <a name="next-steps"></a>次の手順
-   [TIBCO EMS メッセージ記述子のプロパティと値](../core/tibco-enterprise-message-service-message-descriptor-properties.md)  
  
-   [チュートリアル: メッセージ コンテキストのプロパティの使用](../core/tutorial-using-message-context-properties.md)