---
title: 配置、およびアプリケーションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2c86d5f-1849-4b7d-8061-23f156245f5b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f9a34565629c6b1e75966aa306861f13a0cfbed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966387"
---
# <a name="deploy-and-test-the-application"></a>アプリの配置およびテスト
> [!NOTE]
>  このチュートリアルは、BizTalk Server にのみ適用されます。  
  
 このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリをビルド、配置、構成、テストします。  
  
## <a name="build-and-deploy-the-application"></a>アプリのビルドと配置  
  
1.  ソリューション エクスプ ローラーで BizTalk プロジェクト名を右クリックし] をクリックし、**プロパティ**します。  
  
2.  [プロパティ] ページで、[署名] タブをクリックし、[アセンブリの署名] チェック ボックスをオンにして、ドロップダウンから新しい厳密な名前のキー ファイルを作成するオプションを選択します。 表示される手順に従ってファイルを作成します。  
  
3.  プロジェクトへの変更を保存します。 ソリューション エクスプ ローラーでソリューション名を右クリックし] をクリックし、**ソリューションのビルド**します。  
  
4.  プロジェクトが正常にビルド、ソリューション エクスプ ローラーで、ソリューション名を右クリックし、**ソリューションの配置**します。  
  
## <a name="configure-the-application"></a>アプリケーションの構成  
 アプリを構成するには、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] で送受信ポートを作成し、それをオーケストレーションと、オーケストレーションの一部として作成された論理送受信ポートにバインドします。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリが JSON 注文書を受信する受信ポートを作成します。  
  
   1. [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk アプリケーション 1**を右クリックして**受信ポート**、] をポイント**新規**、] をクリックし、**一方向の受信ポート**.  
  
   2. 受信ポートの名前を指定し、左側のペインからをクリックして**受信場所**します。 **受信場所**] タブで [**新規**します。  
  
   3. 受信場所の名前を指定、として、ポートの種類を選択します。**ファイル**、] をクリックし、**構成**します。  
  
   4. 受信場所が JSON 注文書を取得するフォルダーの場所を入力します。 指定`*.json`ファイル マスクおよびクリックとして**OK**します。  
  
   5. **受信パイプライン**ドロップダウン リストで選択**JSONToXml**します。 このカスタム受信パイプラインを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリで作成しました。 省略記号ボタンを右クリックして **([...])** 、パイプラインの横にし、下のボタン**Stage 1 – Deocde コンポーネント**、次の値を指定します。  
  
      - RootNode - `ROOT`  
  
      - RootNodeNamespace –`http://BTSJSON`します。  
  
        これらの値はターゲットの名前空間と、JSON スキーマ ウィザードを使用して JSON 注文書から再生された XML 注文書スキーマのルート ノードの名前を表します。  
  
   6. クリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。  
  
2. JSON 請求書メッセージを送信する送信ポートを作成します。  
  
   1. [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk アプリケーション 1**を右クリックして**送信ポート**、] をポイント**新規**、] をクリックし、**静的の一方向送信ポート**.  
  
   2. 送信ポートの名前を指定、として、ポートの種類を選択します。**ファイル**、] をクリックし、**構成**します。  
  
   3. 送信ポートが送信 JSON 請求書のコピーを作成するフォルダーの場所を入力します。 指定`%MessageID%.json`としてファイル名をクリック**OK**します。  
  
   4. **送信パイプライン**ドロップダウン リストで選択**XmlToJSON**、順にクリックします**OK**します。  
  
   5. クリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。  
  
3. 最後に、オーケストレーションの一部として作成した論理ポートを、作成した物理ポートにバインドしてアプリを構成します。  
  
   1. 右クリック**BizTalk アプリケーション 1**、] をクリックし、**構成**します。  
  
   2. 左側のウィンドウから次のようにクリックします。 **ProcessPO**します。 右側のウィンドウに関連付ける、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストに論理ポートを物理ポートにマップしてクリックして **[ok]** します。  
  
   3. 右クリック**BizTalk アプリケーション 1**、] をクリックし、**開始**します。  
  
## <a name="test-the-application"></a>アプリのテスト  
  
1.  ダウンロードしたサンプルとの間を移動、 **TestMessage**フォルダーをコピー **JsonPurchaseOrder.json**、受信場所に関連付けられているフォルダーに貼り付けます。 ファイルが消えるまで待ちます。  
  
2.  作成した送信ポートに関連付けられているフォルダーに移動します。 なお、***\<GUID\>*.json**フォルダーにファイルが。 ファイルを開いて、それが請求書メッセージであることを確認します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して JSON メッセージの処理](../core/processing-json-messages-using-biztalk-server.md)