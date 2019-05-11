---
title: SendMail |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- SMTP adapters
ms.assetid: a0258619-b195-4c8a-8326-77add6e6f04d
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e05df6001a8f34909c60292050bb784b59112a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399011"
---
# <a name="sendmail"></a>SendMail
SendMail サンプルは、簡易メール転送プロトコル (SMTP) アダプターを使用して、microsoft から電子メール メッセージを送信する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションします。 電子メール メッセージの送信に使用される動的な情報は、プロパティの昇格機能を使用して XML メッセージから取得されます。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、受信 XML 注文書 (PO) メッセージ、次の一連の手順を使用して外部から昇格させたプロパティから取得した情報を使用して電子メール メッセージを送信します。  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、XML PO メッセージを取得します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションの昇格、 **PONumber**と**電子メール**プロパティは、将来簡単にアクセスします。  

3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]動的送信ポートの送信先アドレスを設定して、電子メール メッセージの件名を設定するオーケストレーションは昇格されたプロパティの値を使用します。  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、SMTP アダプターで構築された電子メール メッセージを送信します。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\AdaptersUsage\SendMail\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                    ファイル                     |                                                                                                         説明                                                                                                         |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AssemblyInfo.cs, SendMail.btproj, SendMail.sln |                                                                         このサンプルのプロジェクト、ソリューション、およびアセンブリ情報ファイルを提供します。                                                                         |
|                  Cleanup.bat                   |              必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。               |
|     PropertySchema.xsd、PurchaseOrder.xsd      |                                                           スキーマの昇格するプロパティと提供 XML PO メッセージは、それぞれします。                                                           |
|                」の ReceiveSend.odx                 |   提供、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ内の情報に基づいて、受信 XML PO メッセージを処理し、電子メール メッセージを送信するオーケストレーションです。   |
|               SendMailInput.xml                |                                                                                 XML を使用して指定の PO では、サンプル入力ファイルが含まれています。                                                                                 |
|                   Setup.bat                    | このサンプルを作成および初期化します。 **注:** このセットアップ ファイルが作成し、ポート、およびように、ほとんどの SDK サンプルのセットアップ ファイルよりも、別のメカニズムを使用してバインドします。 Companion .xml ファイルは必要ありません。 |

### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    \<*パスのサンプル*\>\AdaptersUsage\SendMail  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - このサンプルの次の入力フォルダを作成します。  

      \<*パスのサンプル*\>\AdaptersUsage\SendMail\In  

   - コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを開始します。  

     > [!NOTE]
     >  このサンプルを実行する前に、BizTalk がビルド プロセス中および初期化プロセス中にエラーを報告していないことを確認してください。  

     > [!NOTE]
     >  Setup.bat ファイルを実行せずに、このサンプルのプロジェクトを開いてビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。  

     > [!NOTE]
     >  Setup.bat による変更を元に戻すには、Cleanup.bat とすべての受信し、送信ポート SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail で始まる削除を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

3. **BizTalk Server 管理**コンソールで、SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail で始まる受信ポートを探します。 入力の場所として使用するファイル システム上のディレクトリをポイントするには、この受信ポートの受信場所を更新します。  

4. メモ帳などのプログラムを使用して変更した SendMailInput.xml ファイルを変更できるように、**電子メール**要素は、このサンプルで生成された電子メール メッセージを受信する正当な電子メール アドレスを指定します。  

5. クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

6. **BizTalk Server 管理**コンソールで、BizTalk グループのツリーを展開します。  

7. 展開、**プラットフォームの設定**左側のウィンドウのツリーです。  

8. 展開、**アダプター**フォルダー、をクリックして、 **SMTP**ノード、および SMTP アダプターの右側のウィンドウで行をクリックします。  

9. **SMTP - アダプター ハンドラーのプロパティ**ダイアログ ボックスで、をクリックして**プロパティ**します。  

10. **SMTP トランスポートのプロパティ** ダイアログ ボックスで、**プロパティ** タブで、適切な値を指定、 **SMTP サーバー名**と **(電子メールからアドレス)** プロパティ、およびクリック**OK**します。  

     この SMTP アダプタから送信された電子メール メッセージの差出人の電子メール アドレスを作成するこれらの値が使用されます。  

    > [!NOTE]
    >  SMTP サーバーで認証する必要がある場合は、差出人の電子メール アドレスは、認証に使用するのと同じアカウントに属していることを確認する必要があります。  

11. 停止し、オーケストレーションがこれらの変更を採用できるように、BizTalk サービス (BizTalkServerApplication) を再起動します。  

### <a name="to-run-this-sample"></a>このサンプルを実行するには  

1.  入力フォルダーに変更した SendMailInput.xml ファイルのコピーを格納します。  

2.  前の手順で指定した電子メール アドレスに電子メール メッセージの到着を確認します。  

## <a name="see-also"></a>参照  
 [アダプタ サンプル – 使用法](../core/adapter-samples-usage.md)