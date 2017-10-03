---
title: "手順 17: クライアント アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WSClient application
- message enrichment tutorial, WSClient application
- creating, WSClient application
ms.assetid: 2849cd4c-30d0-47ab-8161-fab379d5a548
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8028688f918854d8251f7b059c76642800961088
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-17-create-the-wsclient-application"></a>手順 17: クライアント アプリケーションを作成します。
WSClient.exe (Web サービス クライアント) は、コンソール アプリケーションで記述された[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]を前の手順で Web サービスとして公開するオーケストレーションにデータを送信する方法を示しています。 クライアント アプリケーションは 4 つの順序でパラメーターの入力を受け入れます。 患者名、ミドル ネーム、最後の名、および社会保障番号、それぞれします。 患者の情報を使用する Web サービスを送信するには、次のコマンドライン構文を使用します。  
  
```  
wsclient john henry smith 123456789  
```  
  
### <a name="to-create-the-wsclient-application"></a>クライアント アプリケーションを作成するには  
  
1.  ソリューション エクスプ ローラーで右クリック**ソリューション 'BTAHL7V22Common'**をクリックして**追加**、順にクリック**新しいプロジェクト**です。  
  
2.  **新しいプロジェクトの追加** ダイアログ ボックスで、**プロジェクトの種類** ウィンドウで、をクリックして**Visual c#**し、、**テンプレート** ウィンドウで、をクリックして**コンソール アプリケーション**です。  
  
3.  **名前**フィールドに「**クライアント**です。 **場所**フィールドを参照してください  **\<*ドライブ*>: \Tutorial** をクリックして**OK**です。 ソリューション エクスプ ローラーは、ツリーにクライアントを追加し、Program.cs ファイルが表示されます。  
  
4.  ソリューション エクスプ ローラーで右クリック**クライアント**、クリックして**Web 参照の追加**です。  
  
5.  [Web 参照の追加] ダイアログ ボックスで、**ローカル マシン上のサービスを Web**です。 ローカル コンピューターでは、使用可能な Web サービスを検索し、一覧で表示されます。  
  
6.  ローカル コンピューター上の Web サービスの一覧でクリックして**BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、 をクリックして**Operation_1**、順にクリック**参照の追加**.  
  
7.  Program.cs をダブルクリックします。  
  
8.  次のコードをコピーし、[Program.cs] ウィンドウに貼り付けます。  
  
    ```  
    using System;  
  
    namespace WSClient  
    {  
       class Class1  
       {  
          [STAThread]  
          static void Main(string[] args)  
          {  
             try   
             {  
                localhost.DoorbellRoot req=new WSClient.localhost.DoorbellRoot();  
                req.FirstName=args[0];  
                req.MiddleName=args[1];  
                req.LastName=args[2];  
                req.SSN=args[3];  
                localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort sp=new WSClient.localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort();  
                sp.Operation_1(req);  
             }  
             catch (Exception ex)  
             {  
                Console.WriteLine(ex.Message);  
             }  
          }  
       }  
    }  
    ```  
  
9. ソリューション エクスプ ローラーで右クリック**クライアント**、クリックして**ビルド**です。 成功メッセージが出力ウィンドウに表示されることを確認します。 成功メッセージが表示されない場合のトラブルシューティングを行う**クライアント**です。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]WSClient.exe、実行可能ファイルのコピーを配置、 \<*ドライブ*>: \Tutorial\WSClient\bin\Debug フォルダーです。  
  
 進みます[手順 18.: 新しいメッセージの強化ソリューションのテスト](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)