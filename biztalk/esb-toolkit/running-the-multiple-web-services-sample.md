---
title: "複数の Web を実行しているサービスのサンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b201c7c3-213a-4009-8872-5a4c1cbb8195
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ec54fabb7ed140fd88b5a2d5a07d788805c741e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-multiple-web-services-sample"></a>複数の Web サービス サンプルを実行します。
複数の Web サービス サンプルでは、Windows フォーム クライアント テスト アプリケーション行程入り口サンプルを使用します。  
  
 **複数の Web サービス サンプルを実行するには**  
  
1.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。  
  
2.  Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプル、および Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。  
  
3.  クリア、**を使用して WCF サービス**できるように、クライアント側の日程を利用できますが、チェック ボックスをオンします。  
  
4.  クリックして、**ロード行程**ボタンをクリックし、\Source\Samples\MultipleWebServices\Itineraries フォルダーにあるサンプルの日程のいずれかを選択します。  
  
5.  選択、 **2 つの方法サービス**サービス操作のチェック ボックスをアプリケーションで双方向の日程を実行するようにします。  
  
6.  クリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。  
  
7.  クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。 表示される応答メッセージの待機、**結果**ボックス。  
  
 複数の Web サービス サンプルでの ESB 行程サービスの使用方法については、次を参照してください。 [「複数 Web サービス サンプルの動作](../esb-toolkit/how-the-multiple-web-services-sample-works.md)です。