---
title: "メッセージ強化サンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7015a2fe-3727-48f3-a2ed-c368e0630626
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4ed3b3ebc24a908dfefd70711db0d40638c2d3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-message-enrichment-sample"></a>メッセージ強化サンプルを実行しています。
Message Enrichment サンプルでは、行程入り口サンプルに用意されている、テスト クライアントの Windows フォーム アプリケーションを使用します。  
  
 **Message Enrichment サンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。  
  
2.  Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプル、および Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。  
  
3.  クリア、**を使用して WCF サービス**クライアント側の日程を利用するようにチェック ボックスをオンします。  
  
4.  クリックして、**ロード行程**ボタンをクリックし、\Source\Samples\MessageEnrichment\Itineraries フォルダーにあるサンプルの日程のいずれかを選択します。  
  
5.  クリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\MessageEnrichment\Test\ フォルダーから OrderDoc.xml サンプル メッセージを選択します。  
  
6.  クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。  
  
7.  参照 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml 出力メッセージを表示します。  
  
 Message Enrichment サンプルのしくみについては、次を参照してください。 [「メッセージ強化サンプルの動作](../esb-toolkit/how-the-message-enrichment-sample-works.md)です。