---
title: 'チュートリアル (AS2): 非同期 MDN による AS2 経由で EDI の送信 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83644ac9-7023-4b09-966c-7c41d36f6b11
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e80d5429f109167a91297f69963f0fc46d6e7948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22292410"
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn"></a>チュートリアル (AS2): 非同期 MDN による AS2 経由での EDI の送信
このチュートリアルでは、非同期 MDN による AS2 経由での EDI メッセージの送信用のソリューションを作成する一連の手順について説明します。  このチュートリアルでは、完全なソリューションを単一のコンピューター上で作成およびテストできます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するための前提条件を次に示します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
-   チュートリアルを実行するコンピューターには、インターネット インフォメーション サービス (IIS) 7 がインストールされている必要があります。  
  
-   チュートリアルを実行するコンピューターに 64 ビット版の Windows がインストールされている場合は、BizTalk ホストが 32 ビットのみとマークされていることを確認する必要があります。 IIS の [アプリケーション プールの 32 ビット アプリケーション設定を有効にする] を True に設定する必要があります。 詳細については、次を参照してください。[チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)です。  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-an-asynchronous-mdn"></a>ソリューションで EDI/AS2 メッセージを送信して非同期 MDN を返す方法  
 このソリューションは次の処理を実行します。  
  
1.  一方向の FILE 受信ポートは、Contoso から EDI インターチェンジを受信します。  
  
    > [!NOTE]
    >  この一覧のイベントは、示されている順序で発生するとは限りません。  
  
2.  受信ポートは、パススルー受信パイプラインを使用して、テスト メッセージをそのままメッセージ ボックスにドロップします。  
  
3.  静的な一方向の送信ポートは EDI インターチェンジを取得し、それを AS2 フォーマットにエンコードします。  
  
4.  送信ポートは、EDI インターチェンジを AS2 トランスポート経由で Fabrikam パーティに送信します。  
  
5.  Fabrikam の一方向の受信ポートは、Fabrikam のバーチャル ディレクトリを使用して AS2 メッセージを受信します。 受信パイプラインは、AS2 からの EDI インターチェンジをデコードし、EDI インターチェンジをメッセージ ボックスにドロップします。  
  
6.  また、同じ一方向の受信ポートも、MDN を生成してメッセージ ボックスにドロップします。  
  
7.  静的な一方向の送信ポートは、EDI メッセージを取得します。  
  
8.  静的な一方向の送信ポートは、EDI メッセージをローカル フォルダーに送信します。  
  
9. 動的な一方向の送信ポートは、非同期 MDN を取得します。  
  
10. 動的な一方向の送信ポートは、MDN を Contoso に送信します。  
  
11. 一方向の受信ポートは、MDN を受信してメッセージ ボックスにドロップします。  
  
12. パススルー送信パイプラインを持つ静的な一方向の送信ポートは、MDN を取得します。  
  
13. 一方向の送信ポートは、MDN をローカル フォルダーに送信します。  
  
 次の図では、このソリューションのアーキテクチャを示しています。  
  
 ![非同期 MDN による AS2 の送信](../core/media/343bbfcc-5387-426c-8700-db9738816218.gif "343bbfcc-5387-426c-8700-db9738816218")  
  
## <a name="the-functionality-in-this-solution"></a>このソリューションの機能  
 このチュートリアルの機能には、以下の条件が適用されます。  
  
-   このチュートリアルでは、EDI 機能ではなく AS2 機能について説明します。 このため、AS2 処理に関連するすべてのポートでは、AS2EdiReceive または AS2EdiSend パイプラインでなく、AS2Receive または AS2Send パイプラインを使用します。 AS2 処理に関連しないポートでは、PassThruReceive または PassThruTransmit パイプラインを使用します。  
  
-   状態レポートが有効になっていません。  
  
-   このソリューションは、否認不可データベースに署名、圧縮、暗号化、およびメッセージ ストレージを構成しません。 これらのプロパティを構成する手順については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)です。  
  
## <a name="configuring-and-testing-the-walkthrough"></a>チュートリアルの構成とテスト  
 このソリューションに必要な手順は以下のとおりです。  
  
-   必要なメッセージ スキーマを使用して BizTalk プロジェクトをビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。  
  
-   AS2 メッセージの受信に使用する BTS ISAPI フィルターを有効にします。  
  
-   Contoso からの AS2 メッセージを受信する Fabrikam 仮想ディレクトリを、受信場所で構成したとおりに作成します。  
  
-   Fabrikam からの AS2 メッセージを受信する Contoso 仮想ディレクトリを、受信場所で構成したとおりに作成します。  
  
-   Fabrikam および Contoso 仮想ディレクトリが、Windows SharePoint Services の管理対象から除外されるように指定します。  
  
-   AS2 トランスポート経由で送信される EDI テスト メッセージを受信する一方向 FILE 受信ポートを作成します。 テスト メッセージを受信するローカル フォルダーを作成します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の静的な一方向 HTTP 送信ポートを作成し、EDI ビジネス ドキュメントを含んでいる AS2 メッセージを Fabrikam に送信します。 送信パイプラインとして AS2Send パイプラインを構成します。  
  
-   AS2 メッセージを受信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の一方向の HTTP 受信ポートを作成します。 受信パイプラインとして AS2Receive パイプラインを構成します。 Fabrikam 仮想ディレクトリ経由で AS2 メッセージを受信する受信場所を構成します。  
  
-   メッセージ ペイロードをローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。 ローカル フォルダーを作成します。  
  
    > [!NOTE]
    >  メッセージ ペイロードをサブスクライブする送信ポートがない場合、メッセージ ボックスで中断されます。  
  
-   MDN を Contoso に返す動的な一方向の HTTP 送信ポートを作成します。  
  
    > [!NOTE]
    >  テスト ソリューションが 1 台のコンピューターにはその結果、(Contoso) から AS2 メッセージを送信する一方向の送信ポートと (Fabrikam) から MDN 応答を送信する一方向の送信ポートは、同一コンピューター上です。  
  
-   Fabrikam から MDN 応答を受信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の一方向受信ポートを作成します。  
  
-   MDN をローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。 ローカル フォルダーを作成します。  
  
-   Fabrikam および Contoso の両方にパーティ (取引先) を作成します。  
  
-   両方の取引先に対して、それぞれビジネス プロファイルを作成します。  
  
-   Fabrikam および Contoso のビジネス プロファイル間に AS2 アグリーメントを作成します。 AS2 アグリーメントには、AS2 メッセージを送信し、その応答として非同期 MDN を受信するためのプロパティが含まれます。  
  
-   テスト EDI インターチェンジを使用して、このチュートリアルをテストします。  
  
    > [!NOTE]
    >  テスト メッセージには、EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用できます。 そのファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ folder に保存して出荷されています。 これは、X12 850 メッセージです。  
  
### <a name="configuring-the-walkthrough"></a>チュートリアルの構成  
 ここでは、チュートリアルを構成する手順について説明します。  
  
##### <a name="to-deploy-the-message-schema"></a>メッセージ スキーマを展開するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。  
  
    > [!NOTE]
    >  このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。 いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。  
  
2.  プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の**します。 SamplePO.txt ファイルを使用してソリューションをテストするには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI フォルダーに移動します。 X12_00401_850.xsd スキーマを選択し、クリックして**追加**です。  
  
    > [!NOTE]
    >  異なる EDI スキーマを使用するには、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI フォルダーです。 EDI スキーマは、XSD_SchemaEDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe**スキーマを既定のフォルダーに解凍する XSD_SchemaEDI フォルダー内のファイルです。  
  
3.  アセンブリ キー ファイルを設定し、アセンブリをビルドおよび展開します。  
  
##### <a name="to-enable-the-bts-isapi-filter"></a>BTS ISAPI フィルターを有効にするには  
  
1.  をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
    > [!TIP]
    >  オペレーティング システムによっては、管理ツールの [スタート] メニュー オプションを利用できない場合があります。 このような場合、をクリックして**開始**、 をクリックして**実行**、入力と`inetmgr`インターネット インフォメーション サービス (IIS) マネージャを開きます。  
  
2.  ルート Web サーバーのエントリを選択し、、**機能ビュー**、ダブルクリックして**ハンドラー マッピング**し、操作 ウィンドウでをクリックして**スクリプト マップの追加**です。  
  
    > [!NOTE]
    >  Web サーバー レベルでスクリプト マッピングを構成すると、すべての子 Web サイトに適用するには、このマッピングが発生します。 特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。  
  
3.  **スクリプト マップの追加** ダイアログ ボックスで、入力`BtsHttpReceive.dll`で、**要求パス**フィールドです。  
  
4.  **実行可能ファイル**フィールドで、をクリックして、**省略記号 (...)** ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive です。 BtsHttpReceive.dll を選択し、をクリックして**OK**です。  
  
5.  入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**です。  
  
6.  **要求の制限**ダイアログ ボックスで、**動詞**タブをクリックし**次の動詞のいずれかの**します。 入力`POST`動詞として。  
  
7.  **アクセス** タブで **スクリプト** をクリックし、 **ok**です。  
  
8.  をクリックして**OK** ISAPI 拡張を許可するメッセージが表示されたらをクリックし、**はい**です。  
  
##### <a name="to-configure-the-fabrikam-web-page"></a>Fabrikam Web ページを構成するには  
  
1.  IIS マネージャーを右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**です。  
  
2.  **アプリケーション プールの追加**] ダイアログ ボックスで、入力**BizTalkAppPool**で**名前**、し、[ **.NET Framework V4.0.30210**で、**.NET framework のバージョン**ボックスの一覧です。 **[OK]** をクリックします。  
  
    > [!NOTE]
    >  コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。  
  
3.  選択**アプリケーション プール**の**機能ビュー**選択**BizTalkAppPool**、順にクリック**詳細設定**で**アクション**ウィンドウです。  
  
4.  **詳細設定**ダイアログ ボックスで、 **Identity**省略記号 (...) ボタンをクリックします。  
  
5.  **アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**です。  
  
6.  入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力で**パスワードの確認入力**をクリックして**OK** IIS マネージャーに戻りますを 3 回です。  
  
7.  IIS マネージャーで、開く、**サイト**フォルダーです。 [既定の Web サイト] を右クリックし、[アプリケーションの追加] をクリックします。  
  
8.  **アプリケーションの追加** ダイアログ ボックスで、入力**Fabrikam**で**エイリアス**、順にクリック**選択**です。  
  
9. **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**です。  
  
10. 省略記号 (...) ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**です。  
  
11. をクリックして**テストの設定**に表示されるエラーがないことを確認し、**接続のテスト** ダイアログ ボックス。 **[閉じる]** をクリックし、 **[OK]** をクリックします。  
  
12. IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、、**機能ビュー**をダブルクリックして**認証**です。  
  
13. **認証**を選択**匿名認証**ことを確認し、**ステータス**は**有効**です。 場合、**ステータス**は**無効になっている**、 をクリックして**を有効にする**で、**アクション**ウィンドウです。  
  
##### <a name="to-configure-the-contoso-web-page"></a>Contoso Web ページを構成するには  
  
1.  IIS マネージャーで、開く、**サイト**フォルダーです。 [既定の Web サイト] を右クリックし、[アプリケーションの追加] をクリックします。  
  
2.  **アプリケーションの追加** ダイアログ ボックスで、入力**Contoso**で**エイリアス**、順にクリック**選択**です。  
  
3.  **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**です。  
  
4.  省略記号 (...) ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**です。  
  
5.  をクリックして**テストの設定**に表示されるエラーがないことを確認し、**接続のテスト** ダイアログ ボックス。 **[閉じる]** をクリックし、 **[OK]** をクリックします。  
  
6.  IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、、**機能ビュー**をダブルクリックして**認証**です。  
  
7.  **認証**を選択**匿名認証**ことを確認し、**ステータス**は**有効**です。 場合、**ステータス**は**無効になっている**、 をクリックして**を有効にする**で、**アクション**ウィンドウです。  
  
##### <a name="to-specify-that-the-fabrikam-and-contoso-virtual-directories-are-not-managed-by-windows-sharepoint-services"></a>Fabrikam および Contoso 仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定するには  
  
1.  Windows SharePoint Services がコンピューターにインストールされている場合にをクリックして**開始**、をポイント**すべてのプログラム**、指す**管理ツール**をクリックして**SharePoint 3.0 サーバーの全体管理**です。  
  
    > [!NOTE]
    >  この手順は、チュートリアルを設定するコンピューター上に Windows SharePoint Server がインストールされている場合に実行する必要があります。 実行する場合は、IIS 仮想ディレクトリが Windows SharePoint Server の管理対象から除外されるように指定する必要があります。  
  
2.  **サーバーの全体管理**] ページの [**サーバーの全体管理**をクリックして**アプリケーション管理**です。  
  
3.  **アプリケーション管理**] ページで [**管理パスの定義**です。  
  
4.  **管理パスの定義**] ページの [**新しいパスを追加**で、**パス**テキスト ボックスに、入力`Fabrikam`です。 [**型**、] をクリックして**エクスクルード パス**、順にクリック**OK**です。  
  
5.  Contoso 仮想ディレクトリに対して手順 4. を繰り返します。  
  
6.  閉じる、**管理パスの定義**ページ。  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a>EDI テスト メッセージを受信する受信ポートを作成するには  
  
1.  Windows エクスプローラーを使用して、Contoso から EDI インターチェンジを受信するローカル フォルダーを作成します。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**です。  
  
3.  受信ポートに名前を付けます**RecvISAFromCont**、順にクリック**受信場所**コンソール ツリーでします。  
  
4.  **[新規作成]** をクリックします。  
  
5.  名前、受信場所は、select**ファイル**の**型**、順にクリック**構成**です。  
  
6.  **受信フォルダー**、手順 1. で作成したフォルダーの名前を入力します。  
  
7.  [ファイル マスク] にファイルの拡張子を入力します。 テスト メッセージとして SamplePO.txt ファイルを使用する場合は、入力 **\*.txt**です。 **[OK]** をクリックします。  
  
8.  **受信パイプライン**、既定の**PassThruReceive**です。  
  
9. をクリックして **[ok]**、順にクリック**OK**もう一度です。  
  
10. をクリックして、**受信場所** ノードを右クリックし、受信場所、およびをクリックして**を有効にする**です。  
  
##### <a name="to-create-a-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam"></a>AS2 経由で Fabrikam に EDI インターチェンジを送信する送信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**です。  
  
2.  **送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前として**SendISAToFab**です。  
  
3.  **トランスポート**セクションで、 **HTTP**の**型**、クリックして**構成**です。  
  
4.  **HTTP トランスポートのプロパティ** ダイアログ ボックスの**送信先 URL**、入力**http://localhost/Fabrikam/BTSHttpReceive.dll**です。  
  
5.  クリア**チャンク エンコードを有効にする**、順にクリック**OK**です。  
  
6.  **送信パイプライン** **AS2Send**です。  
  
7.  コンソール ツリーで、次のように選択します。**フィルター**です。 **プロパティ**、入力**BTS です。ReceivePortName**;**演算子**、入力 **==** ; および**値**EDI を受信する受信ポートの名前を入力インターチェンジ (`RecvISAFromCont`)。  
  
8.  **[OK]** をクリックします。  
  
9. クリックして、**送信ポート**管理コンソールで、ノードは、送信ポートを右クリックし、をクリックして**開始**です。  
  
##### <a name="to-create-a-receive-port-for-fabrikam-to-receive-the-as2-message"></a>AS2 メッセージを受信する Fabrikam 用の受信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックし**受信ポート**、指す**新規**、順にクリック**一方向の受信ポート**.  
  
2.  受信ポートに名前を付けます**RecvAS2ForFabrikam**、順にクリック**受信場所**コンソール ツリーでします。  
  
3.  **[新規作成]** をクリックします。  
  
4.  **受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所で、選択**HTTP**の**型**、クリックして**構成**です。  
  
5.  **HTTP トランスポートのプロパティ** ダイアログ ボックスで、入力 **/Fabrikam/BTSHttpReceive.dll**の**仮想ディレクトリと ISAPI 拡張**です。 クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**です。 **[OK]** をクリックします。  
  
6.  選択**AS2Receive**の**受信パイプライン**です。 をクリックして **[ok]**、順にクリック**OK**もう一度です。  
  
7.  をクリックして、**受信場所** ノードを右クリックし、受信場所、およびをクリックして**を有効にする**です。  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>EDI ペイロードをローカル フォルダーに送信する送信ポートを作成するには  
  
1.  Windows エクスプローラーで、EDI インターチェンジを送信する先のローカル フォルダーを作成します。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、送信ポート名**SendEDIToFab**です。 選択**ファイル**の**型**、クリックして**構成**です。  
  
4.  **FILE トランスポートのプロパティ** ダイアログ ボックスの**コピー先フォルダー**、EDI ペイロード用に作成したローカル フォルダーを入力します。  
  
5.  **ファイル名**ファイル名を入力します。 テスト メッセージとして SamplePO.txt ファイルを使用する場合は、入力 **%MessageID%.txt**です。 **[OK]** をクリックします。  
  
6.  既定の**PassThruTransmit**の**送信パイプライン**です。  
  
7.  をクリックして**フィルター**コンソールのツリー、および EDI ペイロードを取得するフィルターのプロパティを追加します。 最初の行での**プロパティ**、入力**BTS です。ReceivePortName**; の**演算子**、入力 **==** ;**値**AS2 を受信する受信ポートの名前を入力してくださいメッセージ (`RecvAS2ForFabrikam`); および**Group by**、受け入れる**と**です。 2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2PayloadMessage**; の**演算子**、入力 **==** ; との**値**、入力**True**です。  
  
8.  **[OK]** をクリックします。  
  
9. クリックして、**送信ポート**ノードは、送信ポートを右クリックし、をクリックして**開始**です。  
  
##### <a name="to-create-a-dynamic-one-way-send-port-to-return-the-mdn"></a>MDN を返す動的な一方向の送信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、をポイント**新規**、クリックして**動的な一方向送信ポート**です。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスで、送信ポート名**Send_MDN**です。  
  
3.  **送信パイプライン**AS2Send を入力します。  
  
4.  をクリックして**フィルター**コンソールのツリー、および EDI ペイロードを取得するフィルターのプロパティを追加します。 最初の行での**プロパティ**、入力**BTS です。ReceivePortName**; の**演算子**、入力 **==** ;**値**AS2 を受信する受信ポートの名前を入力してくださいメッセージ (`RecvAS2ForFabrikam`); および**Group by**、受け入れる**と**です。 2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2AsynchronousMDN**; の**演算子**、入力 **==** ; との**値**、入力**True**です。  
  
5.  **[OK]** をクリックします。  
  
6.  クリックして、**送信ポート**ノードは、送信ポートを右クリックし、をクリックして**開始**です。  
  
##### <a name="to-create-a-receive-port-to-receive-the-mdn-from-fabrikam"></a>Fabrikam から MDN を受信する受信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックし**受信ポート**、指す**新規**、順にクリック**一方向の受信ポート**.  
  
2.  受信ポートに名前を付けます**RecvMDNFromFab**、順にクリック**受信場所**コンソール ツリーでします。  
  
3.  **[新規作成]** をクリックします。  
  
4.  **受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所で、選択**HTTP**の**型**、クリックして**構成**です。  
  
5.  **HTTP トランスポートのプロパティ** ダイアログ ボックスで、入力 **/Contoso/BTSHTTPReceive.dll**の**仮想ディレクトリと ISAPI 拡張**です。 クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**です。 **[OK]** をクリックします。  
  
6.  選択**AS2Receive**の**受信パイプライン**です。 をクリックして **[ok]**、順にクリック**OK**もう一度です。  
  
7.  をクリックして、**受信場所** ノードを右クリックし、受信場所、およびをクリックして**を有効にする**です。  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a>MDN をローカル フォルダーに送信する送信ポートを作成するには  
  
1.  Windows エクスプローラーを使用して、MDN を送信するローカル フォルダーを作成します。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスに、送信ポートの名前します。 選択**ファイル**の**型**、クリックして**構成**です。  
  
4.  **FILE トランスポートのプロパティ** ダイアログ ボックスの**コピー先フォルダー**MDN を送信するために作成したローカル フォルダーを入力します。  
  
5.  **ファイル名**、入力 **%MessageID%.msg**です。をクリックして**OK**です。  
  
6.  既定の**PassThruTransmit**の**送信パイプライン**です。  
  
7.  をクリックして**フィルター**コンソール ツリーでします。 **プロパティ**、入力**BTS です。ReceivePortName**; の**演算子**、入力 **==** ;**値**、(MDNを受信する受信ポートの名前を入力してください`RecvMDNFromFab`);および**Group by**、受け入れる**と**です。 2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2MdnResponseMessage**です。 **演算子**、入力 **==** です。 **値**、入力**True**です。  
  
8.  **[OK]** をクリックします。  
  
9. クリックして、**送信ポート**ノードは、送信ポートを右クリックし、をクリックして**開始**です。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>Fabrikam のパーティとビジネス プロファイルを作成するには  
  
1.  右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。  
  
2.  パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。  
  
    > [!NOTE]
    >  選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。 ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。  
  
3.  パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。  
  
4.  **プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**fabrikam_profile**で、**名前**テキスト ボックス。  
  
    > [!NOTE]
    >  パーティを作成すると、プロファイルも作成されます。 新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。 プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。 **全般** ページで、プロファイルの名前を指定します。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>Contoso のパーティとビジネス プロファイルを作成するには  
  
1.  右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。  
  
2.  パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。  
  
    > [!NOTE]
    >  選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。 ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。  
  
3.  パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。  
  
4.  **プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。  
  
    > [!NOTE]
    >  パーティを作成すると、プロファイルも作成されます。 新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。 プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。 **全般** ページで、プロファイルの名前を指定します。  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a>2 つのビジネス プロファイル間で AS2 アグリーメントを作成するには  
  
1.  右クリック**Contoso_Profile**、をポイント**新規**、クリックして**アグリーメント**です。  
  
2.  **全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。  
  
3.  **プロトコル**ドロップダウン リストで、 **AS2**です。  
  
4.  **2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、 **Fabrikam**です。  
  
5.  **2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **Fabrikam_Profile**です。  
  
     2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブは、一方向の AS2 アグリーメントの構成用です。  
  
6.  次のタスクを実行、 **Contoso が Fabrikam ->** タブです。  
  
    1.  **識別子** ページで、値を入力**AS2-から**と**AS2-に**です。 **AS2-から**、入力`Contoso`です。 **AS2-To**、入力`Fabrikam`です。  
  
    2.  **受信確認 (Mdn)**  ページで、次の操作します。  
  
        1.  選択、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**チェック ボックスをオンします。  
  
            > [!NOTE]
            >  チェック、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**のみが返された MDN 削除されるため、メッセージ ボックスには、このチュートリアルのテストに必要です。 これにより、MDN をサブスクライブする送信ポートを作成し、MDN をローカル ディレクトリに送信して、AS2 トランスミッションを確認できます。  
  
        2.  選択、 **mdn を要求する**チェック ボックスをオンします。  
  
        3.  確認してください、**署名付き mdn を要求してもする**チェック ボックスはオフです。  
  
        4.  選択、**非同期 MDN を要求する**チェック ボックスをオンします。  
  
        5.  **- Receipt-delivery-option (URL)**、入力**http://localhost/Contoso/BTSHttpReceive.dll**です。  
  
        6.  **廃棄する**は既定値に設定に指定した **- Receipt-delivery-option (URL)** プロパティです。 このフィールドの値は、AS2 処理時には使用されません。  
  
    3.  **送信ポート** ページで、EDI インターチェンジを Fabrikam に送信する双方向の送信ポートを関連付けます。 **送信ポート**グリッド 、**名前**列は、空のセルをクリックし、ドロップダウン リストから送信ポートを選択**SendISAToFab**です。  
  
7.  次のタスクを実行、 **Fabrikam が Contoso ->** タブです。  
  
    > [!NOTE]
    >  このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。 アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります **[as2_from]** と**AS2-に**です。  
  
    1.  **識別子** ページで、値を入力**AS2-から**と**AS2-に**です。 **AS2-から**、入力`Fabrikam`です。 **AS2-To**、入力`Contoso`です。  
  
8.  **[適用]** をクリックします。  
  
9. **[OK]** をクリックします。 新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。 新しく追加したアグリーメントは既定で有効になります。  
  
### <a name="testing-the-walkthrough"></a>チュートリアルのテスト  
 ここでは、チュートリアルをテストする方法について説明します。  
  
##### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1.  Windows エクスプローラーで [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial に移動します。 コピー、 **SamplePO.txt**ファイル。  
  
2.  貼り付け、 **SamplePO.txt** Contoso からテスト メッセージを受信するために作成するローカル フォルダーにファイル。  
  
3.  EDI ペイロードを送信するために作成したローカル フォルダーに移動します。 フォルダーに EDI ファイルが含まれていることを確認します。 ファイルおよび元のテスト メッセージを開き、コンテンツが同じであることを確認します。  
  
4.  結果の MDN を送信するために作成したローカル フォルダーに移動します。 フォルダーにテスト ファイルが含まれていることを確認し、ファイルを開いて、これが MDN ファイルであることを確認します。  
  
## <a name="see-also"></a>参照  
 [開発と BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)