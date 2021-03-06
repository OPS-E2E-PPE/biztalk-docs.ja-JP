---
title: チュートリアル (AS2):非同期 MDN による AS2 経由での EDI の送信 |Microsoft Docs
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
ms.openlocfilehash: 05ee6787a0b007c71738106de2b5d9283dcf6f38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250144"
---
# <a name="walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn"></a>チュートリアル (AS2):非同期 MDN による AS2 経由での EDI の送信
このチュートリアルでは、非同期 MDN による AS2 経由での EDI メッセージの送信用のソリューションを作成する一連の手順について説明します。  このチュートリアルでは、完全なソリューションを単一のコンピューター上で作成およびテストできます。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 次に、このトピックの手順を実行するための前提条件を示します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
- チュートリアルを実行するコンピューターには、インターネット インフォメーション サービス (IIS) 7 がインストールされている必要があります。  
  
- チュートリアルを実行するコンピューターに 64 ビット版の Windows がインストールされている場合は、BizTalk ホストが 32 ビットのみとマークされていることを確認する必要があります。 IIS の [アプリケーション プールの 32 ビット アプリケーション設定を有効にする] を True に設定する必要があります。 詳細については、次を参照してください。[チュートリアル 3。AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)します。  
  
## <a name="how-the-solution-sends-an-edias2-message-and-returns-an-asynchronous-mdn"></a>ソリューションで EDI/AS2 メッセージを送信して非同期 MDN を返す方法  
 このソリューションは次の処理を実行します。  
  
1. 一方向の FILE 受信ポートは、Contoso から EDI インターチェンジを受信します。  
  
   > [!NOTE]
   >  この一覧のイベントは、示されている順序で発生するとは限りません。  
  
2. 受信ポートは、パススルー受信パイプラインを使用して、テスト メッセージをそのままメッセージ ボックスにドロップします。  
  
3. 静的な一方向の送信ポートは EDI インターチェンジを取得し、それを AS2 フォーマットにエンコードします。  
  
4. 送信ポートは、EDI インターチェンジを AS2 トランスポート経由で Fabrikam パーティに送信します。  
  
5. Fabrikam の一方向の受信ポートは、Fabrikam のバーチャル ディレクトリを使用して AS2 メッセージを受信します。 受信パイプラインは、AS2 からの EDI インターチェンジをデコードし、EDI インターチェンジをメッセージ ボックスにドロップします。  
  
6. また、同じ一方向の受信ポートも、MDN を生成してメッセージ ボックスにドロップします。  
  
7. 静的な一方向の送信ポートは、EDI メッセージを取得します。  
  
8. 静的な一方向の送信ポートは、EDI メッセージをローカル フォルダーに送信します。  
  
9. 動的な一方向の送信ポートは、非同期 MDN を取得します。  
  
10. 動的な一方向の送信ポートは、MDN を Contoso に送信します。  
  
11. 一方向の受信ポートは、MDN を受信してメッセージ ボックスにドロップします。  
  
12. パススルー送信パイプラインを持つ静的な一方向の送信ポートは、MDN を取得します。  
  
13. 一方向の送信ポートは、MDN をローカル フォルダーに送信します。  
  
    次の図は、このソリューションのアーキテクチャを示します。  
  
    ![非同期 MDN による AS2 の送信](../core/media/343bbfcc-5387-426c-8700-db9738816218.gif "343bbfcc-5387-426c-8700-db9738816218")  
  
## <a name="the-functionality-in-this-solution"></a>このソリューションの機能  
 このチュートリアルの機能には、以下の条件が適用されます。  
  
-   このチュートリアルでは、EDI 機能ではなく AS2 機能について説明します。 このため、AS2 処理に関連するすべてのポートでは、AS2EdiReceive または AS2EdiSend パイプラインでなく、AS2Receive または AS2Send パイプラインを使用します。 AS2 処理に関連しないポートでは、PassThruReceive または PassThruTransmit パイプラインを使用します。  
  
-   状態レポートが有効になっていません。  
  
-   このソリューションは、否認不可データベースに署名、圧縮、暗号化、およびメッセージ ストレージを構成しません。 これらのプロパティを構成する手順については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。  
  
## <a name="configuring-and-testing-the-walkthrough"></a>チュートリアルの構成とテスト  
 このソリューションに必要な手順は以下のとおりです。  
  
- 必要なメッセージ スキーマを使用して BizTalk プロジェクトをビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。  
  
- AS2 メッセージの受信に使用する BTS ISAPI フィルターを有効にします。  
  
- Contoso からの AS2 メッセージを受信する Fabrikam 仮想ディレクトリを、受信場所で構成したとおりに作成します。  
  
- Fabrikam からの AS2 メッセージを受信する Contoso 仮想ディレクトリを、受信場所で構成したとおりに作成します。  
  
- Fabrikam および Contoso 仮想ディレクトリが、Windows SharePoint Services の管理対象から除外されるように指定します。  
  
- AS2 トランスポート経由で送信される EDI テスト メッセージを受信する一方向 FILE 受信ポートを作成します。 テスト メッセージを受信するローカル フォルダーを作成します。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の静的な一方向 HTTP 送信ポートを作成し、EDI ビジネス ドキュメントを含んでいる AS2 メッセージを Fabrikam に送信します。 送信パイプラインとして AS2Send パイプラインを構成します。  
  
- AS2 メッセージを受信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の一方向の HTTP 受信ポートを作成します。 受信パイプラインとして AS2Receive パイプラインを構成します。 Fabrikam 仮想ディレクトリ経由で AS2 メッセージを受信する受信場所を構成します。  
  
- メッセージ ペイロードをローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。 ローカル フォルダーを作成します。  
  
  > [!NOTE]
  >  メッセージ ペイロードをサブスクライブする送信ポートがない場合、メッセージ ボックスで中断されます。  
  
- MDN を Contoso に返す動的な一方向の HTTP 送信ポートを作成します。  
  
  > [!NOTE]
  >  ソリューションのテストが 1 台のコンピューターにはその結果、(Contoso) から AS2 メッセージを送信する一方向の送信ポートと (Fabrikam) から MDN 応答を送信する一方向の送信ポートは、同じコンピューターには。  
  
- Fabrikam から MDN 応答を受信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の一方向受信ポートを作成します。  
  
- MDN をローカル フォルダーにルーティングする静的な一方向の FILE 送信ポート (パススルー送信パイプラインを持つ) を作成します。 ローカル フォルダーを作成します。  
  
- Fabrikam および Contoso の両方にパーティ (取引先) を作成します。  
  
- 両方の取引先に対して、それぞれビジネス プロファイルを作成します。  
  
- Fabrikam および Contoso のビジネス プロファイル間に AS2 アグリーメントを作成します。 AS2 アグリーメントには、AS2 メッセージを送信し、その応答として非同期 MDN を受信するためのプロパティが含まれます。  
  
- テスト EDI インターチェンジを使用して、このチュートリアルをテストします。  
  
  > [!NOTE]
  >  テスト メッセージには、EDI インターフェイス開発チュートリアルで使用した SamplePO.txt ファイルを使用できます。 そのファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\EDI Interface Developer Tutorial\ folder に保存して出荷されています。 これは、X12 850 メッセージです。  
  
### <a name="configuring-the-walkthrough"></a>チュートリアルの構成  
 ここでは、チュートリアルを構成する手順について説明します。  
  
##### <a name="to-deploy-the-message-schema"></a>メッセージ スキーマを展開するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。  
  
   > [!NOTE]
   >  このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。 そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。  
  
2. プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。 SamplePO.txt ファイルを使用してソリューションをテストするには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI フォルダーに移動します。 X12_00401_850.xsd スキーマを選択し、クリックして**追加**します。  
  
   > [!NOTE]
   >  異なる EDI スキーマを使用するには、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_SchemaEDI フォルダー。 EDI スキーマは、XSD_SchemaEDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe**スキーマを既定のフォルダーに解凍する XSD_SchemaEDI フォルダー内のファイル。  
  
3. アセンブリ キー ファイルを設定し、アセンブリをビルドおよび展開します。  
  
##### <a name="to-enable-the-bts-isapi-filter"></a>BTS ISAPI フィルターを有効にするには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
   > [!TIP]
   >  オペレーティング システムによっては、管理ツールの [スタート] メニュー オプションを利用できない場合があります。 このような場合は、次のようにクリックします。**開始**、 をクリック**実行**、入力と`inetmgr`をインターネット インフォメーション サービス (IIS) マネージャーを開きます。  
  
2. ルート Web サーバーのエントリを選択し、**機能ビュー**をダブルクリックします**ハンドラー マッピング**しをクリックして、[操作] ウィンドウで、**スクリプト マップの追加**します。  
  
   > [!NOTE]
   >  Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子の Web サイトに適用するには、このマッピングが発生します。 特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。  
  
3. **スクリプト マップの追加** ダイアログ ボックスに、入力`BtsHttpReceive.dll`で、**要求パス**フィールド。  
  
4. **実行可能ファイル**フィールドに、をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive します。 BtsHttpReceive.dll を選択し、クリックして**OK**します。  
  
5. 入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**します。  
  
6. **要求の制限**ダイアログ ボックスで、**動詞**タブを選び**次の動詞のいずれか**します。 入力`POST`動詞として。  
  
7. **アクセス**] タブで [**スクリプト**順にクリックします**OK**します。  
  
8. をクリックして **[ok]** ISAPI 拡張を許可するメッセージが表示されたら、クリックと**はい**。  
  
##### <a name="to-configure-the-fabrikam-web-page"></a>Fabrikam Web ページを構成するには  
  
1. IIS マネージャーで、右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**します。  
  
2. **アプリケーション プールの追加** ダイアログ ボックスに、入力**BizTalkAppPool**で**名前**、し、 **.NET Framework v4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。 **[OK]** をクリックします。  
  
   > [!NOTE]
   >  コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。  
  
3. 選択**アプリケーション プール**の**機能ビュー**選択**BizTalkAppPool**、順にクリックします**詳細設定**で**アクション**ウィンドウ。  
  
4. **詳細設定**ダイアログ ボックスで、 **Identity**し、省略記号 (...) ボタンをクリックします。  
  
5. **アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**します。  
  
6. 入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力します**パスワードの確認入力**をクリックして **。OK** 3 回の IIS マネージャーに戻ります。  
  
7. IIS マネージャーで、開く、**サイト**フォルダー。 [既定の Web サイト] を右クリックし、[アプリケーションの追加] をクリックします。  
  
8. **アプリケーションの追加** ダイアログ ボックスに、入力**Fabrikam**で**エイリアス**、順にクリックします**選択**します。  
  
9. **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。  
  
10. 省略記号 (...) ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**します。  
  
11. をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。 **[閉じる]** をクリックし、 **[OK]** をクリックします。  
  
12. IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。  
  
13. **認証**を選択します**匿名認証**いることを確認し、**状態**は**有効**します。 場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。  
  
##### <a name="to-configure-the-contoso-web-page"></a>Contoso Web ページを構成するには  
  
1. IIS マネージャーで、開く、**サイト**フォルダー。 [既定の Web サイト] を右クリックし、[アプリケーションの追加] をクリックします。  
  
2. **アプリケーションの追加** ダイアログ ボックスに、入力**Contoso**で**エイリアス**、順にクリックします**選択**します。  
  
3. **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。  
  
4. 省略記号 (...) ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**します。  
  
5. をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。 **[閉じる]** をクリックし、 **[OK]** をクリックします。  
  
6. IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。  
  
7. **認証**を選択します**匿名認証**いることを確認し、**状態**は**有効**します。 場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。  
  
##### <a name="to-specify-that-the-fabrikam-and-contoso-virtual-directories-are-not-managed-by-windows-sharepoint-services"></a>Fabrikam および Contoso 仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定するには  
  
1.  コンピューターに Windows SharePoint Services がインストールされて場合、 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**をクリックして**SharePoint 3.0 サーバーの全体管理**します。  
  
    > [!NOTE]
    >  この手順は、チュートリアルを設定するコンピューター上に Windows SharePoint Server がインストールされている場合に実行する必要があります。 実行する場合は、IIS 仮想ディレクトリが Windows SharePoint Server の管理対象から除外されるように指定する必要があります。  
  
2.  **サーバーの全体管理** ページ **サーバーの全体管理**、 をクリックして**アプリケーション管理**します。  
  
3.  **アプリケーション管理**] ページで [**管理パスの定義**します。  
  
4.  **管理パスの定義**] ページ [**新しいパスを追加**の**パス**テキスト ボックスに、入力`Fabrikam`します。 [**型**、] をクリックして**エクスクルード パス**、順にクリックします**OK**します。  
  
5.  Contoso 仮想ディレクトリに対して手順 4. を繰り返します。  
  
6.  閉じる、**管理パスの定義**ページ。  
  
##### <a name="to-create-a-receive-port-to-receive-the-edi-test-message"></a>EDI テスト メッセージを受信する受信ポートを作成するには  
  
1. Windows エクスプローラーを使用して、Contoso から EDI インターチェンジを受信するローカル フォルダーを作成します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**します。  
  
3. 受信ポートに名前を付けます**RecvISAFromCont**、 をクリックし、**受信場所**コンソール ツリーで。  
  
4. **[新規]** をクリックします。  
  
5. [受信場所の名前**ファイル**の**型**、] をクリックし、**構成**。  
  
6. **受信フォルダー**、手順 1. で作成したフォルダーの名前を入力します。  
  
7. [ファイル マスク] にファイルの拡張子を入力します。 テスト メッセージとして SamplePO.txt ファイルを使用する場合は、入力 **\*.txt**します。 **[OK]** をクリックします。  
  
8. **受信パイプライン**、既定値はそのまま使用**PassThruReceive**します。  
  
9. をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
10. をクリックして、**受信場所**ノードを右クリックし、受信場所をクリックして**を有効にする**。  
  
##### <a name="to-create-a-send-port-to-send-the-edi-interchange-over-as2-to-fabrikam"></a>AS2 経由で Fabrikam に EDI インターチェンジを送信する送信ポートを作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート**します。  
  
2. **送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前として**SendISAToFab**します。  
  
3. **トランスポート**セクションで、 **HTTP**の**型**、 をクリックし、**構成**します。  
  
4. **HTTP トランスポートのプロパティ** ダイアログ ボックスの**送信先 URL**、入力 **http://localhost/Fabrikam/BTSHttpReceive.dll**します。  
  
5. クリア**チャンク エンコードを有効にする**、 をクリックし、 **OK**。  
  
6. **送信パイプライン**、 **AS2Send**します。  
  
7. コンソール ツリーで、選択**フィルター**します。 **プロパティ**、入力**BTS します。ReceivePortName**; の**演算子**、入力**==**; と**値**EDI を受信する受信ポートの名前を入力します。インターチェンジ (`RecvISAFromCont`)。  
  
8. **[OK]** をクリックします。  
  
9. をクリックして、**送信ポート**、管理コンソール内のノードは、送信ポートを右クリックし をクリックし、**開始**。  
  
##### <a name="to-create-a-receive-port-for-fabrikam-to-receive-the-as2-message"></a>AS2 メッセージを受信する Fabrikam 用の受信ポートを作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**.  
  
2. 受信ポートに名前を付けます**RecvAS2ForFabrikam**、 をクリックし、**受信場所**コンソール ツリーで。  
  
3. **[新規]** をクリックします。  
  
4. **受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所の選択、 **HTTP**の**型**、順にクリックします**構成**します。  
  
5. **HTTP トランスポートのプロパティ** ダイアログ ボックスに、入力 **/Fabrikam/BTSHttpReceive.dll**の**仮想ディレクトリと ISAPI 拡張**します。 クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**します。 **[OK]** をクリックします。  
  
6. 選択**AS2Receive**の**受信パイプライン**します。 をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
7. をクリックして、**受信場所**ノードを右クリックし、受信場所をクリックして**を有効にする**。  
  
##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>EDI ペイロードをローカル フォルダーに送信する送信ポートを作成するには  
  
1. Windows エクスプローラーで、EDI インターチェンジを送信する先のローカル フォルダーを作成します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  
  
3. **送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**SendEDIToFab**します。 選択**ファイル**の**型**、 をクリックし、**構成**します。  
  
4. **FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**、EDI ペイロード用に作成したローカル フォルダーを入力します。  
  
5. **ファイル名**ファイル名を入力します。 テスト メッセージとして SamplePO.txt ファイルを使用する場合は、入力 **%MessageID%.txt**します。 **[OK]** をクリックします。  
  
6. 既定の**PassThruTransmit**の**送信パイプライン**します。  
  
7. をクリックして**フィルター**コンソールで、ツリーし、EDI ペイロードの集荷に対してフィルターのプロパティを追加します。 最初の行での**プロパティ**、入力**BTS します。ReceivePortName**は**演算子**、入力 **==** は**値**AS2 を受信する受信ポートの名前を入力メッセージ (`RecvAS2ForFabrikam`); と**でグループ化**、受け入れる**と**します。 2 行目の**プロパティ**、入力**EdiIntAS.IsAS2PayloadMessage**は**演算子**、入力**==**; と**値**、入力**True**します。  
  
8. **[OK]** をクリックします。  
  
9. をクリックして、**送信ポート**ノードは、送信ポートを右クリックし、順にクリックします**開始**します。  
  
##### <a name="to-create-a-dynamic-one-way-send-port-to-return-the-mdn"></a>MDN を返す動的な一方向の送信ポートを作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**動的な一方向送信ポート**します。  
  
2. **送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**Send_MDN**します。  
  
3. **送信パイプライン**AS2Send を入力します。  
  
4. をクリックして**フィルター**コンソールで、ツリーし、EDI ペイロードの集荷に対してフィルターのプロパティを追加します。 最初の行での**プロパティ**、入力**BTS します。ReceivePortName**は**演算子**、入力 **==** は**値**AS2 を受信する受信ポートの名前を入力メッセージ (`RecvAS2ForFabrikam`); と**でグループ化**、受け入れる**と**します。 2 行目の**プロパティ**、入力**EdiIntAS.IsAS2AsynchronousMDN**は**演算子**、入力**==**; と**値**、入力**True**します。  
  
5. **[OK]** をクリックします。  
  
6. をクリックして、**送信ポート**ノードは、送信ポートを右クリックし、順にクリックします**開始**します。  
  
##### <a name="to-create-a-receive-port-to-receive-the-mdn-from-fabrikam"></a>Fabrikam から MDN を受信する受信ポートを作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**.  
  
2. 受信ポートに名前を付けます**RecvMDNFromFab**、 をクリックし、**受信場所**コンソール ツリーで。  
  
3. **[新規]** をクリックします。  
  
4. **受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所の選択、 **HTTP**の**型**、順にクリックします**構成**します。  
  
5. **HTTP トランスポートのプロパティ** ダイアログ ボックスに、入力 **/Contoso/BTSHTTPReceive.dll**の**仮想ディレクトリと ISAPI 拡張**します。 クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**します。 **[OK]** をクリックします。  
  
6. 選択**AS2Receive**の**受信パイプライン**します。 をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
7. をクリックして、**受信場所**ノードを右クリックし、受信場所をクリックして**を有効にする**。  
  
##### <a name="to-create-a-send-port-to-send-the-mdn-to-a-local-folder"></a>MDN をローカル フォルダーに送信する送信ポートを作成するには  
  
1. Windows エクスプローラーを使用して、MDN を送信するローカル フォルダーを作成します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  
  
3. **送信ポートのプロパティ** ダイアログ ボックスに、送信ポートの名前します。 選択**ファイル**の**型**、 をクリックし、**構成**します。  
  
4. **FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**MDN を送信するために作成したローカル フォルダーを入力します。  
  
5. **ファイル名**、入力 **%MessageID%.msg**します。**[OK]** をクリックします。  
  
6. 既定の**PassThruTransmit**の**送信パイプライン**します。  
  
7. クリックして**フィルター**コンソール ツリーでします。 **プロパティ**、入力**BTS します。ReceivePortName**は**演算子**、入力 **==** は**値**、(MDNを受信する受信ポートの名前を入力します。`RecvMDNFromFab`);および**でグループ化**、受け入れる**と**します。 2 番目の行の**プロパティ**、入力**EdiIntAS.IsAS2MdnResponseMessage**します。 **演算子**、入力 **==** します。 **値**、入力**True**します。  
  
8. **[OK]** をクリックします。  
  
9. をクリックして、**送信ポート**ノードは、送信ポートを右クリックし、順にクリックします**開始**します。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-fabrikam"></a>Fabrikam のパーティとビジネス プロファイルを作成するには  
  
1. 右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。  
  
2. パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。  
  
   > [!NOTE]
   >  選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。 ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。  
  
3. パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。  
  
4. **プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力 **[fabrikam_profile]** で、**名前**テキスト ボックス。  
  
   > [!NOTE]
   >  パーティを作成すると、プロファイルも作成されます。 新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。 プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。 **全般** ページで、プロファイルの名前を指定します。  
  
##### <a name="to-create-a-party-and-a-business-profile-for-contoso"></a>Contoso のパーティとビジネス プロファイルを作成するには  
  
1. 右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 をポイント**新規**、 をクリックし、**パーティ**します。  
  
2. パーティの名前を入力、**名前**テキスト ボックス、およびクリック **[ok]** します。  
  
   > [!NOTE]
   >  選択して、**ローカル BizTalk 受信パーティまたはサポートがこのパーティからメッセージを送信したメッセージを処理**チェック ボックスをオンをホストしている同じ組織のパーティの作成中であること指定できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。 ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。  
  
3. パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。  
  
4. **プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力**Contoso_Profile**で、**名前**テキスト ボックス。  
  
   > [!NOTE]
   >  パーティを作成すると、プロファイルも作成されます。 新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。 プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。 **全般** ページで、プロファイルの名前を指定します。  
  
##### <a name="to-create-an-as2-agreement-between-the-two-business-profiles"></a>2 つのビジネス プロファイル間で AS2 アグリーメントを作成するには  
  
1.  右クリック**Contoso_Profile**、 をポイント**新規**、 をクリックし、**契約**します。  
  
2.  **全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。  
  
3.  **プロトコル**ドロップダウン リストで、 **AS2**します。  
  
4.  **2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Fabrikam**します。  
  
5.  **2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **[fabrikam_profile]** します。  
  
     2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは、一方向の AS2 アグリーメントの構成用です。  
  
6.  次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。  
  
    1.  **識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。 **AS2-から**、入力`Contoso`します。 **AS2-To**、入力`Fabrikam`します。  
  
    2.  **受信確認 (Mdn)** ページで、次の操作を行います。  
  
        1.  選択、 **MessageBox にルーティング/配信の受信 MDN を処理する**チェック ボックスをオンします。  
  
            > [!NOTE]
            >  チェック、 **MessageBox にルーティング/配信の受信 MDN を処理する**のみが返された MDN の削除を MessageBox にために、このチュートリアルをテストするため必要です。 これにより、MDN をサブスクライブする送信ポートを作成し、MDN をローカル ディレクトリに送信して、AS2 トランスミッションを確認できます。  
  
        2.  選択、 **mdn を要求する**チェック ボックスをオンします。  
  
        3.  必ず、**署名付き MDN を要求**チェック ボックスをオフします。  
  
        4.  選択、**非同期 MDN を要求する**チェック ボックスをオンします。  
  
        5.  **- Receipt-delivery-option (URL)**、入力 **http://localhost/Contoso/BTSHttpReceive.dll**します。  
  
        6.  **ディス ポジション-通知-に**は既定値に設定に指定した **- Receipt-delivery-option (URL)** プロパティ。 このフィールドの値は、AS2 処理時には使用されません。  
  
    3.  **送信ポート** ページで、EDI インターチェンジを Fabrikam に送信する双方向送信ポートを関連付けます。 **送信ポート**グリッドで、**名前**列で空のセルしボックスの一覧から、送信ポートを選択します。 **SendISAToFab**します。  
  
7.  次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。  
  
    > [!NOTE]
    >  このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。 アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります **[as2_from]** と**AS2-に**します。  
  
    1.  **識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。 **AS2-から**、入力`Fabrikam`します。 **AS2-To**、入力`Contoso`します。  
  
8.  **[適用]** をクリックします。  
  
9. **[OK]** をクリックします。 新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。 新しく追加したアグリーメントは既定で有効になります。  
  
### <a name="testing-the-walkthrough"></a>チュートリアルのテスト  
 ここでは、チュートリアルをテストする方法について説明します。  
  
##### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1. Windows エクスプローラーで [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial に移動します。 コピー、 **SamplePO.txt**ファイル。  
  
2. 貼り付け、 **SamplePO.txt** Contoso からテスト メッセージを受信するために作成したローカル フォルダーにファイル。  
  
3. EDI ペイロードを送信するために作成したローカル フォルダーに移動します。 フォルダーに EDI ファイルが含まれていることを確認します。 ファイルおよび元のテスト メッセージを開き、コンテンツが同じであることを確認します。  
  
4. 結果の MDN を送信するために作成したローカル フォルダーに移動します。 フォルダーにテスト ファイルが含まれていることを確認し、ファイルを開いて、これが MDN ファイルであることを確認します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server AS2 ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)