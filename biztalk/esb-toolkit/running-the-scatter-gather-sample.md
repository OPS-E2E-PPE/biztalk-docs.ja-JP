---
title: スキャッター/ギャザー サンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53676974-ea1f-4c95-9dbb-98fff92286fa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda345b5a96f36125432e454b5f239f756a76652
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023760"
---
# <a name="running-the-scatter-gather-sample"></a>スキャッター/ギャザー サンプルを実行します。
スキャッター/ギャザー サンプルを使用して、Windows フォームは、旅行プラン サービスの機能がこのパターンでどのように適用されるかを示すために、旅行プラン サンプルで提供されるクライアント アプリケーションをテストします。  
  
 **スキャッター/ギャザー サンプルを実行するには**  
  
1. GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。  
  
2. Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルをし、Esb.Itinerary.Test.exe という名前のアプリケーションを起動します。  
  
3. をクリックして、 **LoadItinerary**ボタンをクリックし、\Source\Samples\ScatterGather\Itineraries フォルダーから ScatterGatherItinerary.xml という名前のサンプルの旅行プランを選択します。  
  
4. クリア、**は Request Response**サービス操作のチェック ボックスを一方向の旅行プランをアプリケーションが実行されるようにします。  
  
5. (省略可能)設定、 **WCF サービスを使用して**受信場所のチェック ボックス、OnRamp.Itinerary.Response.WCF を使用するアプリケーションの場合、既定ではなく OnRamp.Itinerary.Response.SOAP 受信場所。  
  
6. をクリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。  
  
7. をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。 応答メッセージを表示するフォルダー \Source\Samples\DynamicResolution\Test\FileDrop\Out を開きます。  
  
   散布図を収集サンプルが ESB スケジュール サービスを使用する方法については、[、スキャッター/ギャザー サンプルのしくみ](../esb-toolkit/how-the-scatter-gather-sample-works.md)を参照してください。