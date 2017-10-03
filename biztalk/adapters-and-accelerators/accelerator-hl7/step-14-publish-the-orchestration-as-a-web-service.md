---
title: "手順 14: Web サービスとしてのオーケストレーションの公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- publishing, orchestrations
- Web services, orchestrations
- message enrichment tutorial, orchestrations
- publishing, Web services
- message enrichment tutorial, Web services
ms.assetid: 8f29a7be-a679-4ca6-a648-35338d9e9e98
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd7707ded0951eb1141368a91e7fe8f533e8241a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a>手順 14: Web サービスとしてのオーケストレーションを公開します。
このステップでは、BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開します。  
  
 Web サービスとしてのオーケストレーションを発行する前に [biztalkserverisolatedhost] のログオン アカウントは、BizTalk データベースにアクセス権を持つため、BizTalk 分離ホスト ユーザー グループの一部ことを確認する必要があります。 これは、機能は、このチュートリアルでは、Web サービス公開ウィザードによって作成される SOAPReceivePort 受信場所の受信ハンドラーが BizTalkServerIsolatedHost、BizTalkServerApplication ではないため必要です。 受信ハンドラーは BizTalkServerIsolatedHost は、SOAP アダプターは BizTalk プロセスではなく、IIS プロセスで実行されるためです。  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a>アクセスするために、SOAPReceivePort の特権の受信場所  
  
1.  BizTalk Server 管理コンソールで、[**ホスト インスタンス**で、**プラットフォームの設定**] ノードを右クリックして**BizTalkServerIsolatedHost**をクリックして**プロパティ**です。 [プロパティ] ダイアログ ボックスで、**構成**です。 注、**ログオン**アカウント。  
  
2.  コンピューターの管理 ダイアログ ボックスで **グループ**で、**ローカル ユーザーとグループ** ノードをダブルクリック**BizTalk 分離ホスト ユーザー**です。 ログオン アカウントする場合**BizTalkServerIsolatedHost**のメンバーではない**BizTalkServerIsolatedHost**グループに追加します。  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードを実行するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、**ソリューション 'BTAHL7V22Common'**です。 **ツール** メニューのをクリックして**BizTalk Web サービス公開ウィザード**です。  
  
2.  **BizTalk Web サービス公開ウィザード**の**へようこそ**  ページで、をクリックして**次**です。  
  
3.  **Web サービスの作成**] ページで、[ **BizTalk オーケストレーション web サービスとして公開**、クリックして**[次へ]**です。  
  
4.  **BizTalk アセンブリ** ページの 、 **BizTalk アセンブリ ファイル (\*.dll)**フィールドを参照または入力  **\<*ドライブ*>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**、 をクリックして**BTAHL7 Project.dll**、 をクリックして**開く**、順にクリック**次**.  
  
5.  **オーケストレーションとポート** ページで、すべてのノードが選択されていることを確認し、をクリックして**次**です。  
  
6.  **Web サービスのプロパティ** ページの**web サービスのターゲット名前空間**、型**http://localhost**、順にクリック**次**です。  
  
7.  **Web サービス プロジェクト**] ページで、[ **web サービスへの匿名アクセスを許可する**と**次のアプリケーションに受信場所を作成する BizTalk**です。 選択**BizTalk アプリケーション 1**アプリケーションです。 既定の保持、**場所**フィールドです。 をクリックして**次**を既定のプロジェクトの場所を受け入れるようにします。  
  
8.  **Web サービス プロジェクトの概要** ページで、をクリックして**作成**ASP.NET Web サービス プロジェクトを生成します。  
  
9. **[完了]** をクリックして、ウィザードを終了します。  
  
10. BizTalk Server 管理コンソールを開きます。 コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**.  
  
11. をクリックして**受信場所**を右クリックして**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、クリックして**プロパティ**.  
  
12. 受信場所のプロパティ ダイアログ ボックスで、**受信パイプライン** **Microsoft.BizTalk.DefaultPipelines.XMLReceive**クリックしてドロップダウン リストから**OK**.  
  
13. 右クリック**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、クリックして**を有効にする**です。  
  
 進みます[手順 15: 構成、送信ポートと受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)