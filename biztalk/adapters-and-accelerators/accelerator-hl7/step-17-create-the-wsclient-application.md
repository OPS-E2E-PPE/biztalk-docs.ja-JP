---
title: 手順 17:WSClient アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WSClient application
- message enrichment tutorial, WSClient application
- creating, WSClient application
ms.assetid: 2849cd4c-30d0-47ab-8161-fab379d5a548
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9238e94168060c8e8853bbd8108ae62a57397d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288846"
---
# <a name="step-17-create-the-wsclient-application"></a>手順 17:WSClient アプリケーションを作成します。
WSClient.exe (Web サービス クライアント) で記述されたコンソール アプリケーションは、[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]は、前の手順で Web サービスとして公開するオーケストレーションにデータを送信する方法を示しています。 WSClient アプリケーションは、4 つの入力の順序でパラメーターを受け取る: 患者名、ミドル ネーム、名、および社会保障番号の末尾をそれぞれします。 患者の情報を Web サービスを送信するには、次のコマンドライン構文を使用します。  
  
```  
wsclient john henry smith 123456789  
```  
  
### <a name="to-create-the-wsclient-application"></a>WSClient アプリケーションを作成するには  
  
1. ソリューション エクスプ ローラーで右クリックして**ソリューション 'BTAHL7V22Common'**、 をクリックして**追加**、 をクリックし、**新しいプロジェクト**します。  
  
2. **新しいプロジェクトの追加** ダイアログ ボックスで、**プロジェクトの種類**ウィンドウで、をクリックして**Visual c#** し、**テンプレート**ウィンドウで、をクリックします **。コンソール アプリケーション**します。  
  
3. **名前**フィールドに「 **WSClient**します。 **場所**フィールドを参照 **\<*ドライブ*\>: \Tutorial**、順にクリックします**OK**します。 ソリューション エクスプ ローラーがツリーに WSClient を追加し、Program.cs ファイルが表示されます。  
  
4. ソリューション エクスプ ローラーで右クリックして**WSClient**、 をクリックし、 **Web 参照の追加**します。  
  
5. [Web 参照の追加] ダイアログ ボックスで、**の Web サービス、ローカル マシン**します。 ローカル コンピューターでは、利用可能な Web サービスを検索し、一覧で表示されます。  
  
6. ローカル コンピューター上の Web サービスの一覧でクリックして**BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、 をクリックして**Operation_1**、順にクリックします**参照の追加**.  
  
7. Program.cs をダブルクリックします。  
  
8. 次のコードをコピーし、[Program.cs] ウィンドウに貼り付けます。  
  
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
  
9. ソリューション エクスプ ローラーで右クリックして**WSClient**、 をクリックし、**ビルド**します。 成功メッセージが出力ウィンドウに表示されることを確認します。 成功メッセージが表示されない場合のトラブルシューティングを行う**WSClient**します。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] WSClient.exe、実行可能ファイルのコピーを配置、 \<*ドライブ*\>: \Tutorial\WSClient\bin\Debug フォルダー。  
  
   続行する[手順 18。新しいメッセージ強化ソリューションのテスト](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)