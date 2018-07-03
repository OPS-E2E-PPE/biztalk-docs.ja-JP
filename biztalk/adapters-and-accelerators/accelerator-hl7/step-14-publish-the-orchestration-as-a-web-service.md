---
title: '手順 14: Web サービスとしてのオーケストレーションの公開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- publishing, orchestrations
- Web services, orchestrations
- message enrichment tutorial, orchestrations
- publishing, Web services
- message enrichment tutorial, Web services
ms.assetid: 8f29a7be-a679-4ca6-a648-35338d9e9e98
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64bcc47364cca427f2fc02a807528e7105a40837
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992083"
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a>手順 14: Web サービスとしてのオーケストレーションを公開します。
この手順では、BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開します。  
  
 Web サービスとしてのオーケストレーションを公開する前に、BizTalk データベースにアクセスできるように、[biztalkserverisolatedhost] のログオン アカウントが、BizTalk 分離ホスト ユーザー グループの一部があることを確認する必要があります。 これは、機能は、このチュートリアルでは、Web サービス公開ウィザードによって作成される SOAPReceivePort 受信場所の受信ハンドラーは、[biztalkserverisolatedhost]、[biztalkserverapplication] ではないため、必要です。 受信ハンドラーは、SOAP アダプタは BizTalk プロセスではなく、IIS プロセスで実行されるので、BizTalkServerIsolatedHost が。  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a>特権、SOAPReceivePort の受信場所をアクセスできるようにするには  
  
1.  BizTalk Server 管理コンソールで **ホスト インスタンス**で、**プラットフォームの設定**ノードを右クリックして**BizTalkServerIsolatedHost**順にクリックします**プロパティ**します。 [プロパティ] ダイアログ ボックスで、**構成**します。 注、**ログオン**アカウント。  
  
2.  コンピューターの管理] ダイアログ ボックスで [**グループ**で、**ローカル ユーザーとグループ**ノードをダブルクリック**BizTalk 分離ホスト ユーザー**。 場合のログオン アカウント**BizTalkServerIsolatedHost**のメンバーではない**BizTalkServerIsolatedHost**グループに追加します。  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードを実行するには  
  
1. ソリューション エクスプ ローラーの Visual Studio で、**ソリューション 'BTAHL7V22Common'** します。 **ツール** メニューのをクリックして**BizTalk Web サービス公開ウィザード**します。  
  
2. **BizTalk Web サービス公開ウィザード**の**へようこそ**  ページで **次**します。  
  
3. **Web サービスの作成**] ページで、[ **BizTalk オーケストレーション web サービスとして発行**、順にクリックします**次**します。  
  
4. **BizTalk アセンブリ**ページで、 **BizTalk アセンブリ ファイル (\*.dll)** フィールドを参照または入力 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**、 をクリックして**BTAHL7 Project.dll**、 をクリックして**オープン**、 をクリックし、 **次へ**.  
  
5. **オーケストレーションおよびポート** ページで、すべてのノードが選択すると、クリックしてであることを確認**次**します。  
  
6. **Web サービスのプロパティ** ページの**web サービスのターゲット名前空間**、型**http://localhost**、順にクリックします**次**します。  
  
7. **Web サービス プロジェクト**] ページで、[ **web サービスへの匿名アクセスを許可する**と**作成 BizTalk 受信場所を次のアプリケーションに**します。 選択**BizTalk アプリケーション 1**アプリケーション。 既定の保持、**場所**フィールド。 をクリックして**次**を既定のプロジェクトの場所を受け入れるようにします。  
  
8. **Web サービス プロジェクトの概要**] ページで [**作成**ASP.NET Web サービス プロジェクトを生成します。  
  
9. **[完了]** をクリックして、ウィザードを終了します。  
  
10. BizTalk Server 管理コンソールを開きます。 コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**.  
  
11. をクリックして**受信場所**を右クリックして**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、 をクリックし、**プロパティ**.  
  
12. [受信場所のプロパティ] ダイアログ ボックスで、**受信パイプライン**を選択します**Microsoft.BizTalk.DefaultPipelines.XMLReceive**クリックしてドロップダウン リストから **[ok]**.  
  
13. 右クリック**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、 をクリックし、**を有効にする**します。  
  
    続行する[手順 15: 構成、送信ポートと受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)します。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)