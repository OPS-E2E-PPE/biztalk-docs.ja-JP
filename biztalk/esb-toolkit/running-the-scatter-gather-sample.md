---
title: "スキャッター/ギャザー サンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53676974-ea1f-4c95-9dbb-98fff92286fa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dcafa519aac074ccb339373a591b590846c9341
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-scatter-gather-sample"></a>スキャッター/ギャザー サンプルを実行します。
スキャッター/ギャザー サンプルでは、Windows フォームは、このパターンが行程サービスの機能を適用する方法を示すために、行程入り口サンプルに用意されているクライアント アプリケーションをテストします。  
  
 **スキャッター/ギャザー サンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。  
  
2.  Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプル、および Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。  
  
3.  クリックして、 **LoadItinerary**ボタンをクリックし、サンプル itinerary \Source\Samples\ScatterGather\Itineraries フォルダーから ScatterGatherItinerary.xml をという名前を選択します。  
  
4.  クリア、**要求応答の**サービス操作のチェック ボックスをアプリケーションで一方向の日程を実行するようにします。  
  
5.  (省略可能)設定、 **WCF サービスを使用して**する場合は、アプリケーション、OnRamp.Itinerary.Response.WCF を使用する チェック ボックスの受信場所、既定ではなく OnRamp.Itinerary.Response.SOAP 受信場所。  
  
6.  クリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。  
  
7.  クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。 応答メッセージを表示するフォルダー \Source\Samples\DynamicResolution\Test\FileDrop\Out を開きます。  
  
 散布図を収集サンプルが、ESB 行程サービスでどのように使用する方法については、次を参照してください。 [「スキャッター/ギャザー サンプルの動作](../esb-toolkit/how-the-scatter-gather-sample-works.md)です。