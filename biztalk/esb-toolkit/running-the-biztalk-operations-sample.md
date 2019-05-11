---
title: BizTalk 操作サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e91d4e57-ba94-4730-8c5a-4c96902f313f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 681a7a2d99c7488c94d3b824fa3e7d707db435ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292532"
---
# <a name="running-the-biztalk-operations-sample"></a>BizTalk 操作サンプルを実行しています。
Microsoft BizTalk 操作サンプルでは、Windows フォームのテスト クライアント アプリケーションを使用して、BizTalk 操作 Web サービスのメソッドを実行し、結果を表示します。 それを実行して、独自のサービス指向アーキテクチャ (SOA) や ESB アプリケーション内の BizTalk 操作 Web サービスの使用方法を紹介するコードをチェックするテスト クライアント プロジェクトを開くことができます。  
  
 Windows エクスプ ローラーで \Samples\BizTalkOperations\bin\Debug、という名前のフォルダーを開き Microsoft.Practices.ESB.BizTalkOperations.Test.Client.exe アプリケーションを実行します。  
  
 図 1 は、BizTalk 操作 Web サービスのテスト用クライアント アプリケーションを示します。 このアプリケーションを使用して BizTalk 操作 Web サービスのすべての関数を実行することができます。 アプリケーションでは、ツリー ビューの形式で結果が表示され、サービスによって返されるメッセージが表示されます。  
  
 ![Web サービス テスト](../esb-toolkit/media/ch6-webservicetest.gif "Ch6 WebServiceTest")  
  
 **図 1**  
  
 **BizTalk 操作 Web サービス テスト クライアント**  
  
 すべてのパラメーターを必要としない BizTalk 操作 Web サービスのメソッドを実行するには、アプリケーション ウィンドウの左側にある適切なボタンをクリックします。 メソッドの入力パラメーターを必要とは、ウィンドウの上部にあるドロップダウン リストで、メソッドを選択の入力 をクリックし、必要な場合、パラメーター値、**サービスの呼び出し**ボタンをクリックします。  
  
## <a name="how-the-sample-works"></a>サンプルのしくみ  
 サンプル アプリケーションでは、ESB BizTalk 操作 Web サービスのインスタンスを作成し、アプリケーションで選択した設定に応じて、適切なメソッドを呼び出します。 選択したサービス メソッドにパラメーターとしてアプリケーションのコントロールに入力する値を渡すし、アプリケーション ウィンドウに表示するサービス メソッドから出力を収集します。