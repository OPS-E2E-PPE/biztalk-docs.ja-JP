---
title: TIBCO EMS メッセージ コンテキスト プロパティの使用 |Microsoft Docs
description: BizTalk Server オーケストレーションで TIBCO Enterprise Message System のメッセージ記述子フィールドを使用します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c4c095969483905cf30403e4831e4f2df8296b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394572"
---
# <a name="message-context-properties-in-tibco-ems"></a>TIBCO EMS のメッセージ コンテキスト プロパティ

## <a name="tibcoemspropertiesdll"></a>TibcoEMSProperties.dll
TIBCO Enterprise Message System のメッセージ記述子フィールドは、BizTalk Server オーケストレーションからアクセスするへの参照を追加する必要があります**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**をプロジェクトにします。 このアセンブリにある **\<TIBCO EMS_Adapter_installation_directory\>\bin**します。 この TIBCO EMS プロパティ スキーマを参照すると、追加のコンテキスト プロパティは、さまざまな BizTalk Server 開発ツール (たとえば、オーケストレーション デザイナーでのメッセージの割り当て図形) でアクセスできます。  
  
## <a name="access-context-properties"></a>コンテキスト プロパティへのアクセスします。  
 コンテキスト プロパティにアクセスするには、で指定した使用可能なコンテキスト プロパティの 1 つ、TIBCO EMS 名前空間。 BizTalk Adapter for TIBCO EMS にバインドのポートから受信したメッセージのコンテキスト プロパティを読み取りするには、式の中で、次の構文を使用します。  
  
```  
Message(TibcoEMS.Property)  
```  
  
 詳細については、次を参照してください。 [TIBCO Enterprise Message Service メッセージ記述子プロパティ](../core/tibco-enterprise-message-service-message-descriptor-properties.md)します。  
  
 BizTalk Server で、メッセージは変更できません。 そのため、するメッセージ コンテキスト プロパティの値を割り当てるには、新しいメッセージを作成、(場合によっては、既存のメッセージの割り当て)、メッセージの内容を設定して、必要なプロパティを設定します。  
  
 に TIBCO EMS 用 BizTalk アダプターにバインドされている送信ポートに送信されたメッセージを TIBCO EMS のコンテキスト プロパティを割り当てるに、メッセージ代入演算子を使用し、TIBCO EMS 名前空間で使用できるプロパティのいずれかを指定します。 構文は次のとおりです。  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="next-steps"></a>次のステップ
-   [TIBCO EMS メッセージ記述子のプロパティと値](../core/tibco-enterprise-message-service-message-descriptor-properties.md)  
  
-   [チュートリアル: メッセージ コンテキスト プロパティを使用します。](../core/tutorial-using-message-context-properties.md)