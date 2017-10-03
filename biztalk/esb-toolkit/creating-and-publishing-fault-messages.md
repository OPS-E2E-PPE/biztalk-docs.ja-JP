---
title: "エラー メッセージを作成およびパブリッシュ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc7ba1d9-b647-4cba-a3dc-4400505ff51f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57833cefedcf53b7355c17cf97d429d2eb988819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-publishing-fault-messages"></a>作成、およびエラー メッセージの公開
例外管理フレームワークの機能を使用して例外を管理する方法を理解するためは、ここでは、ESB アプリケーションへのメッセージの送信に基づいた一般的なシナリオを示します。  
  
 システムへの請求書を送信してユーザーのシナリオで構成されます。 オーケストレーションで請求書を処理中に、BizTalk ビジネス ルール エンジンは、データの一部が正しくないため、アプリケーション例外をスローします。 ビジネス プロセスは、例外をキャッチ、他人や他のことができます、メッセージを解決しを再送信メッセージを処理するシステムに害のあるメッセージを送信する必要があります。  
  
 ESB 失敗オーケストレーション例外ルーティング機能を使用して、プロセスの手順は次に示します。  
  
1.  例外ハンドラーでコードがエラーを検出し、呼び出すことによって、エラー メッセージを作成、 **CreateFaultMessage**メソッドを次のコード例に示すようにします。  
  
    ```csharp  
    // Create fault exception message.  
    faultMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.CreateFaultMessage();  
    ```  
  
2.  ESB 例外処理機構では、フォールト メッセージ コンテキストに、エラーの説明を自動的に挿入 (たとえば、「ビジネス ルール エンジンがスローされました除算 0 による LoanProcessing ポリシーの処理中に。」) です。  
  
3.  ESB 例外処理機構は自動的にフォールト メッセージ コンテキストにエラーに固有のプロパティとアプリケーション固有のプロパティを昇格し、現在の環境から値を設定します。 これらのプロパティは次のとおりです。  
  
    -   **アプリケーション**(自動的に入力されます)  
  
    -   **DateTime** (自動設定された UTC 値として)  
  
    -   **説明**(自動設定された-例外メッセージ)  
  
    -   **ErrorType** (自動設定された、例外の種類)  
  
    -   **MachineName** (自動設定された、現在のサーバー名)  
  
    -   **スコープ**(自動設定された、現在の例外ハンドラーを含むスコープ図形)  
  
    -   **ServiceName** (自動設定された、オーケストレーション名)  
  
    -   **ServiceInstanceID**(自動設定された —、オーケストレーション インスタンス ID を GUID として)  
  
4.  例外ハンドラーのコードは、次のコード例に示すように、必要に応じて、エラー メッセージの他のプロパティを設定します。  
  
    ```csharp  
    // Set fault message properties.  
    faultMsg.Body.FailureCategory = "MessageBuild";  
    faultMsg.Body.FaultCode = 1000;  
    faultMsg.Body.FaultDescription = "Some error occurred";  
    faultMsg.Body.FaultSeverity =  
       Microsoft.Practices.ESB.ExceptionHandling.FaultSeverity.Severe;  
    ```  
  
5.  ESB 例外処理機構は、現在を自動的にシリアル化**例外**オブジェクト、エラー メッセージにします。  
  
6.  必要に応じて、例外ハンドラーのコードは現在のオーケストレーション メッセージの ESB フォールト メッセージを使用して、追加できます、 **AddMessage (faultMsg、messageToAdd)**メソッドです。 このメソッドは、シリアル化し、次のコード例に示すように、すべてのコンテキスト プロパティを含むメッセージが引き続き発生します。  
  
    ```csharp  
    // Add other current orchestration messages to the fault message.  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, approvedRequestMsg);  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, DeniedRequestMsg, @"c:\temp");  
    ```  
  
7.  例外ハンドラーのコードでは、直接バインド ポートを使用してメッセージ ボックス データベースに ESB フォールト メッセージを発行します。  
  
8.  公開が成功すると、次のイベントが発生します。  
  
    -   オーケストレーションまたは送信ポートのサブスクリプションでは、ESB フォールト メッセージを処理でき、そのコンテキスト プロパティの値を持つ完全な任意の追加メッセージを抽出することができます。  
  
    -   グローバル例外ハンドラー (送信ポート) は、ESB の管理ポータルを ESB フォールト メッセージを自動的に公開します。