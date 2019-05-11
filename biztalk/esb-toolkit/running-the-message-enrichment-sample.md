---
title: メッセージ強化サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7015a2fe-3727-48f3-a2ed-c368e0630626
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afa17db3817a485f11c63a88c796c93e6ec5354b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242862"
---
# <a name="running-the-message-enrichment-sample"></a>メッセージ強化サンプルを実行しています。
メッセージ強化サンプルでは、行程導入サンプルで提供される Windows フォームのテスト クライアント アプリケーションを使用します。  
  
 **Message Enrichment サンプルを実行するには**  
  
1. GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。  
  
2. Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルをし、Esb.Itinerary.Test.exe という名前のアプリケーションを起動します。  
  
3. クリア、 **WCF サービスを使用して**クライアント側の旅行プランを利用できるようにチェック ボックスをオンします。  
  
4. をクリックして、**ロード行程**ボタンをクリックし、\Source\Samples\MessageEnrichment\Itineraries フォルダーにあるサンプルのスケジュールのいずれかを選択します。  
  
5. をクリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\MessageEnrichment\Test\ フォルダーから OrderDoc.xml サンプル メッセージを選択します。  
  
6. をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。  
  
7. C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out 参照\\%MessageID%.xml 出力メッセージを確認します。  
  
   メッセージ強化サンプルのしくみについては、次を参照してください。 [、メッセージ強化サンプルのしくみ](../esb-toolkit/how-the-message-enrichment-sample-works.md)します。