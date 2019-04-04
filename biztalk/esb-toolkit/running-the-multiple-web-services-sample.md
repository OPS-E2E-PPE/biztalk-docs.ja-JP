---
title: 複数の Web を実行しているサービスのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b201c7c3-213a-4009-8872-5a4c1cbb8195
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765d9785bde94f363ea56178f3cc0f500381d4e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997523"
---
# <a name="running-the-multiple-web-services-sample"></a>複数の Web サービス サンプルを実行します。
複数の Web サービス サンプルでは、行程導入サンプルで提供される Windows フォームのテスト クライアント アプリケーションを使用します。  
  
 **複数の Web サービス サンプルを実行するには**  
  
1. GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。  
  
2. Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルをし、Esb.Itinerary.Test.exe という名前のアプリケーションを起動します。  
  
3. クリア、 **WCF サービスを使用して**クライアント側の旅行プランを利用できるようにチェック ボックスをオンします。  
  
4. をクリックして、**ロード行程**ボタンをクリックし、\Source\Samples\MultipleWebServices\Itineraries フォルダーにあるサンプルのスケジュールのいずれかを選択します。  
  
5. 選択、**方法の 2 つのサービス**サービス操作のチェック ボックスの双方向の旅行プランをアプリケーションが実行されるようにします。  
  
6. をクリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。  
  
7. をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。 表示される応答メッセージの待機、**結果**ボックス。  
  
   ESB スケジュール サービスを複数の Web サービス サンプルで使用する方法については、[、複数 Web サービス サンプルのしくみ](../esb-toolkit/how-the-multiple-web-services-sample-works.md)を参照してください。