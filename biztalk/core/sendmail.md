---
title: "SendMail |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- SMTP adapters
ms.assetid: a0258619-b195-4c8a-8326-77add6e6f04d
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6cf0243eccb6a38dc121cfe06a60e30fa0c26c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="sendmail"></a>SendMail
SendMail サンプルは、簡易メール転送プロトコル (SMTP) アダプターを使用して、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションから電子メール メッセージを送信する方法を示します。 電子メール メッセージの送信に使用される動的な情報は、プロパティの昇格機能を使用して XML メッセージから取得します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、受信 XML 発注書 (PO) メッセージから、次の一連の手順を使用して昇格させたプロパティから取得した情報を使用して電子メール メッセージを送信します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションが、受信 XML PO メッセージを取得します。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションの昇格、 **PONumber**と**電子メール**プロパティ アクセスを後で簡単にします。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションは、昇格されたプロパティの値を使用して、動的送信ポートの送信先アドレス、および電子メール メッセージの件名を設定します。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションは、SMTP アダプターを使用して、構築された電子メール メッセージを送信します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\AdaptersUsage\SendMail\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs、SendMail.btproj、SendMail.sln|このサンプルのプロジェクト ファイル、ソリューション ファイル、およびアセンブリ情報ファイルを提供します。|  
|Cleanup.bat|必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。|  
|PropertySchema.xsd、PurchaseOrder.xsd|昇格するプロパティのスキーマ、および XML PO メッセージのスキーマを提供します。|  
|ReceiveSend.odx|受信 XML PO メッセージを処理し、メッセージの情報に基づいて電子メール メッセージを送信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを提供します。|  
|SendMailInput.xml|XML を使用して PO を指定したサンプル入力ファイルが含まれています。|  
|Setup.bat|このサンプルを作成および初期化します。 **注:** SDK サンプルについては、ファイルのほとんどのセットアップとは異なる機構を使用して、このセットアップ ファイルを作成し、ポートをバインドします。 companion .xml ファイルは必要ありません。|  
  
### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\AdaptersUsage\SendMail  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   このサンプルの次の入力フォルダを作成します。  
  
         \<*パスのサンプル*\>\AdaptersUsage\SendMail\In  
  
    -   コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを開始します。  
  
        > [!NOTE]
        >  このサンプルを実行する前に、BizTalk がビルド プロセス中および初期化プロセス中にエラーを報告していないことを確認してください。  
  
        > [!NOTE]
        >  Setup.bat ファイルを実行せずに、このサンプルのプロジェクトを開いてビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。  
  
        > [!NOTE]
        >  Setup.bat による変更を元に戻すには、Cleanup.bat を実行し、SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail で始まるすべての受信ポートと送信ポートを削除します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
3.  **BizTalk Server 管理コンソール**コンソールで、SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail で始まる受信ポートを検索します。 この受信ポートの受信場所を更新して、ファイル システムのディレクトリをポイントし、入力場所に使用します。  
  
4.  メモ帳などのプログラムを使用して SendMailInput.xml ファイルを変更できるように、**電子メール**要素は、このサンプルで生成された電子メール メッセージを受信する正当な電子メール アドレスを指定します。  
  
5.  をクリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
6.  **BizTalk Server 管理コンソール**コンソールで、BizTalk グループ ツリーを展開します。  
  
7.  展開して、**プラットフォームの設定**左ペインのツリーです。  
  
8.  展開、**アダプター**フォルダーで、をクリックして、 **SMTP**ノード、および SMTP アダプターの右側のペインで行をダブルクリックします。  
  
9. **SMTP - アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**です。  
  
10. **SMTP トランスポートのプロパティ** ダイアログ ボックスで、**プロパティ** タブで、適切な値を指定して、 **SMTP サーバー名**と**(電子メールからアドレス)**プロパティ、およびクリック**OK**です。  
  
     これらの値を使用して、この SMTP アダプタから送信するすべての電子メール メッセージの差出人の電子メール アドレスを構築します。  
  
    > [!NOTE]
    >  SMTP サーバーで認証する必要がある場合は、差出人の電子メール アドレスが、認証に使用するアカウントと同じアカウントに所属していることを確認する必要があります。  
  
11. BizTalk サービス (BizTalkServerApplication) を停止してから再起動し、オーケストレーションがこれらの変更を採用するようにします。  
  
### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  変更した SendMailInput.xml ファイルを入力フォルダーにコピーします。  
  
2.  電子メール メッセージが、前の手順で指定した電子メール メッセージに届くことを確認します。  
  
## <a name="see-also"></a>参照  
 [アダプタ サンプル – 使用法](../core/adapter-samples-usage.md)