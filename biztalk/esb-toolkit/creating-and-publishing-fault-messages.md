---
title: エラー メッセージの作成と発行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc7ba1d9-b647-4cba-a3dc-4400505ff51f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6d57b5f6ed8a5df00e5c1447b54167b3cfa688b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394694"
---
# <a name="creating-and-publishing-fault-messages"></a>作成、およびエラー メッセージの公開
例外管理フレームワークの機能を使用して例外を管理する方法を理解するために、ここでは、ESB アプリケーションへのメッセージの送信に基づく一般的なシナリオを示します。  
  
 システムへの請求書を送信するユーザーのシナリオで構成されます。 オーケストレーションで請求書の処理の中は、BizTalk ビジネス ルール エンジンは、データの一部が正しくないためにアプリケーション例外をスローします。 ビジネス プロセスは、例外をキャッチに別のユーザーまたはシステムをメッセージを修正し、メッセージの処理を再送信している問題のあるメッセージを送信する必要があります。  
  
 ESB 失敗オーケストレーションの例外ルーティング機能を使用して、プロセスの手順は次に示します。  
  
1.  例外ハンドラーのコードがエラーを検出し、呼び出すことによってエラー メッセージを作成します、 **CreateFaultMessage**メソッドを次のコード例に示すようにします。  
  
    ```csharp  
    // Create fault exception message.  
    faultMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.CreateFaultMessage();  
    ```  
  
2.  ESB 例外メカニズムでは、エラー メッセージのコンテキストに、エラーの説明を自動的に挿入 (たとえば、「ビジネス ルール エンジンがスローされました除算を 0 個のエラーによって LoanProcessing ポリシーの処理中に。」)。  
  
3.  ESB 例外処理機構は自動的にフォールト メッセージ コンテキストにエラーに固有のプロパティおよびアプリケーション固有のプロパティを昇格し、現在の環境から値を設定します。 これらのプロパティ、次に示します。  
  
    -   **アプリケーション**(自動的に設定されます)  
  
    -   **DateTime** (自動設定、UTC 値として)  
  
    -   **説明**(自動的に設定されます-例外メッセージ)  
  
    -   **ErrorType** (自動的に設定されます: 例外の種類)  
  
    -   **MachineName** (自動的に設定されます: 現在のサーバー名)  
  
    -   **スコープ**(自動的に設定されます: 現在の例外ハンドラーを含むスコープ図形)  
  
    -   **ServiceName** (自動的に設定されます: オーケストレーション名)  
  
    -   **ServiceInstanceID**(自動的に設定されます: オーケストレーションのインスタンス ID を GUID として)  
  
4.  例外ハンドラーのコードは、次のコード例に示すように、必要に応じて、エラー メッセージの他のプロパティを設定します。  
  
    ```csharp  
    // Set fault message properties.  
    faultMsg.Body.FailureCategory = "MessageBuild";  
    faultMsg.Body.FaultCode = 1000;  
    faultMsg.Body.FaultDescription = "Some error occurred";  
    faultMsg.Body.FaultSeverity =  
       Microsoft.Practices.ESB.ExceptionHandling.FaultSeverity.Severe;  
    ```  
  
5.  ESB 例外処理機構は、現在自動的にシリアル化します。**例外**オブジェクトを、エラー メッセージにします。  
  
6.  ESB エラー メッセージを使用する、例外ハンドラーのコードが現在のオーケストレーションのメッセージを追加する必要に応じて、 **AddMessage (faultMsg、messageToAdd)** メソッド。 このメソッドは、シリアル化し、次のコード例に示すように、すべてのコンテキスト プロパティを含むメッセージが引き続き発生します。  
  
    ```csharp  
    // Add other current orchestration messages to the fault message.  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, approvedRequestMsg);  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, DeniedRequestMsg, @"c:\temp");  
    ```  
  
7.  例外ハンドラーのコードでは、直接バインド ポートを使用してメッセージ ボックス データベースに、ESB エラー メッセージを発行します。  
  
8.  発行が成功すると、次のイベントが発生します。  
  
    -   オーケストレーションまたは送信ポートのサブスクリプションでは、ESB のエラー メッセージを処理でき、そのコンテキスト プロパティの値を備えた任意の追加メッセージを抽出することができます。  
  
    -   グローバル例外ハンドラー (送信ポート) は、ESB 管理ポータルに、ESB エラー メッセージを自動的に発行します。