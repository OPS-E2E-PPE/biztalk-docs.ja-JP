---
title: "BizTalk Operations サンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e91d4e57-ba94-4730-8c5a-4c96902f313f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57480e6020b2ab262d7d9db522b9dd2f79aa49cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-biztalk-operations-sample"></a>BizTalk Operations サンプルを実行します。
Microsoft BizTalk Operations サンプルでは、Windows フォーム クライアントのテスト アプリケーションを使用して BizTalk Operations Web サービスのメソッドを実行し、結果を表示します。 それを実行して、独自のサービス指向アーキテクチャ (SOA) および ESB アプリケーションで、BizTalk Operations Web サービスを使用する方法を表示するコードをチェックするテスト クライアント プロジェクトを開くことができます。  
  
 Windows エクスプ ローラーで、\Samples\BizTalkOperations\bin\Debug、名前が付いたフォルダーを開き Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe アプリケーションを実行します。  
  
 図 1 は、BizTalk Operations Web サービスに対してクライアント テスト アプリケーションを示します。 このアプリケーションを使用して、BizTalk Operations Web サービスのすべての関数を実行することができます。 アプリケーションは、ツリー ビューの形式で結果が表示され、サービスによって返されるメッセージが表示されます。  
  
 ![Web サービス テスト](../esb-toolkit/media/ch6-webservicetest.gif "Ch6 WebServiceTest")  
  
 **図 1**  
  
 **BizTalk Operations Web サービス テスト用クライアント**  
  
 アプリケーション ウィンドウの左側にある適切なボタンをクリックするだけで、すべてのパラメーターが不要な BizTalk Operations Web サービスのメソッドを実行します。 メソッドの入力パラメーターが必要では、ウィンドウの上部にあるドロップダウン リストでメソッドを選択して、入力パラメーターの値を必要とし、をクリックして、**サービスの呼び出し**ボタンをクリックします。  
  
## <a name="how-the-sample-works"></a>このサンプルのしくみ  
 サンプル アプリケーションは、ESB BizTalk Operations Web サービスをインスタンス化し、アプリケーションで選択した設定に応じて、適切なメソッドを呼び出します。 選択したサービス メソッドにパラメーターとしてアプリケーションのコントロールに入力した値を渡すし、アプリケーション ウィンドウに表示するサービスのメソッドから出力を収集します。