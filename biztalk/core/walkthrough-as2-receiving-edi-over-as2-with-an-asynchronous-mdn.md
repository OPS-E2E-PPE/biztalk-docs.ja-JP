---
title: チュートリアル (AS2):非同期 MDN による AS2 経由での EDI の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3962e4-0525-4194-8cf1-b90664f1a139
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 591672c11e44b08d123b944e033c1e0b49910289
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320764"
---
# <a name="walkthrough-as2-receiving-edi-over-as2-with-an-asynchronous-mdn"></a>チュートリアル (AS2):非同期 MDN による AS2 経由での EDI の受信
このチュートリアルでは、AS2 トランスポート経由で EDI メッセージを受信して同期 MDN を返すソリューションを作成する、一連の手順について説明します。  

## <a name="prerequisites"></a>前提条件  
 次に、このトピックの手順を実行するための前提条件を示します。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  

- チュートリアルを実行するコンピューターには、インターネット インフォメーション サービス (IIS) 7 がインストールされている必要があります。  

- チュートリアルを実行するコンピューターに 64 ビット版の Windows がインストールされている場合は、BizTalk ホストが 32 ビットのみとマークされていることを確認する必要があります。 IIS の [アプリケーション プールの 32 ビット アプリケーション設定を有効にする] を True に設定する必要があります。 詳細については、次を参照してください。[チュートリアル 3。AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)します。  

## <a name="how-the-solution-receives-an-edi-interchange-and-returns-an-asynchronous-mdn"></a>ソリューションで EDI インターチェンジを受信して非同期 MDN を返す方法  
 このソリューションは次の処理を実行します。  

1. 取引先から HTTP 経由で、EDI インターチェンジが含まれた AS2 メッセージを受信し、EDIINT/AS2 からインターチェンジをデコードします。  

   > [!NOTE]
   >  この一覧のイベントは、示されている順序で発生するとは限りません。  

2. MDN 応答を生成して、MessageBox に配置します。  

3. 動的送信ポートによるメッセージ MDN を取得します。  

4. 非同期メッセージ MDN を取引先に返します。  

5. インターチェンジの EDI 形式を内部 XML 形式に変換し、メッセージ ボックスに格納します。  

6. PassThruTransmit パイプラインを持つ送信ポートが、メッセージ XML ファイルを MessageBox から取得します。  

7. 送信ポートが、EDI インターチェンジ XML ファイルを Contoso というパーティのフォルダーに送信します。  

   次の図は、このソリューションのアーキテクチャを示します。  

   ![非同期 MDN による AS2 の受信](../core/media/bts-configuring-the-receiving-of-edi-over-as2-with-an-asynchronous-mdnc.gif "bts_Configuring_the_Receiving_of_EDI_Over_AS2_with_an_Asynchronous_MDNc")  

## <a name="the-functionality-in-this-solution"></a>このソリューションの機能  
 このチュートリアルの機能には、以下の条件が適用されます。  

-   EDI 受信確認は生成されません。 方法については、EDI 受信確認を生成する[チュートリアル (X12):EDI インターチェンジの受信と受信確認の送信](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)します。 「AS2 トランスポート経由で EDI 受信確認を送信する[チュートリアル (AS2)。非同期 MDN による AS2 経由での EDI の送信](../core/walkthrough-as2-sending-edi-over-as2-with-an-asynchronous-mdn.md)します。  

-   このソリューションは、EDIFACT エンコードではなく X12 エンコードを使用するインターチェンジを対象に設計されています。  

    > [!NOTE]
    >   EDIFACT エンコードに使用される構成は、X12 エンコードに使用される構成とよく似ています。  

-   EDI の種類の検証および拡張された検証は、受信インターチェンジに対して実行されます。  

-   AS2 レポートおよび EDI レポートが有効になり、インターチェンジの状態レポートに表示するトランザクション セットが保存されます。  

-   このソリューションは、否認不可データベースに署名、圧縮、暗号化、およびメッセージ ストレージを構成しません。 これらのプロパティを構成する手順については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。  

## <a name="configuring-and-testing-the-walkthrough"></a>チュートリアルの構成とテスト  
 このソリューションに必要な手順は以下のとおりです。  

- 必要なメッセージ スキーマを使用して BizTalk プロジェクトをビルドおよび展開し、受信したインターチェンジを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。  

- AS2 メッセージの受信に使用する BTS ISAPI フィルターを有効にします。  

- Fabrikam からの AS2 メッセージを受信する Contoso 仮想ディレクトリを、受信場所で構成したとおりに作成します。  

- MDN を Contoso から受信する Fabrikam 仮想ディレクトリを作成します。  

- Contoso および Fabrikam 仮想ディレクトリが、Windows SharePoint Services の管理対象から除外されるように指定します。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の静的な一方向 HTTP 受信ポートを作成し、EDI ビジネス ドキュメントを含んでいる AS2 メッセージを取引先から受信します。 受信パイプラインとして AS2EDIReceive パイプラインを構成します。  

- 受信した AS2 メッセージに応答して MDN を送信する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の動的な一方向 HTTP 送信ポートを作成します。  

  > [!NOTE]
  >  この送信ポートは、EdiIntAS.IsAS2AsynchronousMDN プロパティ (AS2EdiReceive パイプラインにより True に設定されている) および関連付けトークンに基づいて、MDN をサブスクライブします。 メッセージのヘッダーにある Receipt-Delivery-Notification 行のアドレスに MDN を送信するには、送信ポートが動的になっている必要があります。  

- 静的な一方向 FILE 送信ポートを作成し、EDI ペイロード (XML 形式) をローカル フォルダーにルーティングします。 ローカル フォルダーを作成します。  

- Fabrikam および Contoso の両方にパーティ (取引先) を作成します。  

- 両方の取引先に対して、それぞれビジネス プロファイルを作成します。  

- Fabrikam および Contoso のビジネス プロファイル間に AS2 アグリーメントを作成します。 AS2 アグリーメントには、AS2 メッセージを送信し、その応答として非同期 MDN を受信するためのプロパティが含まれます。  

- Fabrikam および Contoso のビジネス プロファイル間に、X12 メッセージを受信する X12 アグリーメントを作成します。  

- AS2 チュートリアル ファイルの一部として同梱されている HTTP 送信者ユーティリティを使用して、このソリューションをテストします。 このユーティリティは、EDI インターチェンジを含むテスト用 AS2 メッセージを、AS2 トランスポートを経由して送信します。 このユーティリティは、AS2 トランスポートを経由して、EDI インターチェンジが含まれた AS2 テスト メッセージを送信します (この X12_00401_864.edi は AS2 チュートリアルにも付属しています)。 このチュートリアルに使用する HTTP 送信者とテスト メッセージは、チュートリアルに付属しているバージョンと同じです。  

### <a name="configuring-the-walkthrough"></a>チュートリアルの構成  
 ここでは、チュートリアルを構成する手順について説明します。  

##### <a name="to-deploy-the-message-schema"></a>メッセージ スキーマを展開するには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.btproj プロジェクトを開きます。  

   > [!NOTE]
   >  このプロジェクトは AS2 チュートリアルに付属し、テスト メッセージと共に使用する 864 スキーマが含まれています。  

   > [!NOTE]
   >  このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。 そうでない場合は、次を参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。  

2. 右クリックし、**スキーマ**ソリューション エクスプ ローラーでプロジェクトをクリックして**プロパティ**します。 をクリックして、**署名** タブで、プロジェクト デザイナー、**アセンブリに署名**チェック ボックスをオンし、ドロップダウン リストから選択します**新規**を作成するために必要な値を指定し、厳密な名前キー ファイルです。 変更を保存し、プロジェクトのプロパティ ウィンドウを閉じます。  

3. Schemas.btproj をビルドおよび展開します。  

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

6. 要求の制限 ダイアログ ボックスで、選択、**動詞**タブを選び**次の動詞のいずれかの**します。 入力`POST`動詞として。  

7. **アクセス**] タブで [**スクリプト**順にクリックします**OK**します。  

8. をクリックして **[ok]** ISAPI 拡張を許可するメッセージが表示されたら、クリックと**はい**。  

##### <a name="to-configure-the-contoso-web-page"></a>Contoso Web ページを構成するには  

1. IIS マネージャーで、右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**します。  

2. **アプリケーション プールの追加** ダイアログ ボックスに、入力**BizTalkAppPool**で**名前**、し、 **.NET Framework v4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。 **[OK]** をクリックします。  

   > [!NOTE]
   >  コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。  

3. 選択**アプリケーション プール**、機能ビューの選択で**BizTalkAppPool**、順にクリックします**詳細設定**で、**アクション**ウィンドウです。  

4. **詳細設定**ダイアログ ボックスで、 **Identity**  をクリックし、**省略記号 (...)** ボタンをクリックします。  

5. **アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**します。  

6. 入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力します**パスワードの確認入力**をクリックして **。OK** 3 回の IIS マネージャーに戻ります。  

7. IIS マネージャーで、開く、**サイト**フォルダー。 右クリックし、**既定の Web サイト**ノードをクリックして**アプリケーションの追加**します。  

8. **アプリケーションの追加** ダイアログ ボックスに、入力**Contoso**で、**エイリアス**テキスト ボックス、およびクリック**選択**。  

9. **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。  

10. **物理パス**、クリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive します。  

11. をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。 **[閉じる]** をクリックし、 **[OK]** をクリックします。  

12. IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。  

13. **認証**] ページで、[**匿名認証**いることを確認し、**状態**は**有効**。 場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。  

##### <a name="to-configure-the-fabrikam-web-page"></a>Fabrikam Web ページを構成するには  

1. IIS マネージャーで、開く、**サイト**フォルダー。 右クリックし、**既定の Web サイト**ノードをクリックして**アプリケーションの追加**します。  

2. **アプリケーションの追加** ダイアログ ボックスに、入力**Fabrikam**で**エイリアス**、順にクリックします**選択**します。  

3. **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。  

4. **物理パス**、クリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 \fabrikam します。  

5. をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。 **[閉じる]** をクリックし、 **[OK]** をクリックします。  

6. IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。  

7. **認証**] ページで、[**匿名認証**いることを確認し、**状態**は**有効**。 場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。  

##### <a name="to-specify-that-your-virtual-directory-is-not-managed-by-windows-sharepoint-services"></a>仮想ディレクトリが Windows SharePoint Services の管理対象から除外されるように指定するには  

1.  コンピューターに Windows SharePoint Services がインストールされて場合、 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**をクリックして**SharePoint 3.0 サーバーの全体管理**します。  

    > [!NOTE]
    >  この手順は、チュートリアルを設定するコンピューター上に Windows SharePoint Server がインストールされている場合に実行する必要があります。 実行する場合は、IIS 仮想ディレクトリが Windows SharePoint Server の管理対象から除外されるように指定する必要があります。  

2.  **サーバーの全体管理** ページ **サーバーの全体管理**、 をクリックして**アプリケーション管理**します。  

3.  **アプリケーション管理**] ページで [**管理パスの定義**します。  

4.  **管理パスの定義**] ページ [**新しいパスを追加**の**パス**テキスト ボックスに、入力**Contoso**します。 [**型**、] をクリックして**エクスクルード パス**、順にクリックします**OK**します。  

5.  Fabrikam 仮想ディレクトリに対して手順 4. を繰り返します。  

##### <a name="to-create-a-receive-port-to-receive-the-edi-interchange-over-as2-from-fabrikam"></a>Fabrikam から AS2 経由で EDI インターチェンジを受信する受信ポートを作成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート**します。  

2. 受信ポートの名前を指定し、をクリックし、**受信場所**コンソール ツリーでします。  

3. **[新規]** をクリックします。  

4. [受信場所の名前**HTTP**の**型**、] をクリックし、**構成**。  

5. **仮想ディレクトリと ISAPI 拡張**、入力`/Contoso/BTSHTTPReceive.dll`します。  

6. 選択、**失敗した要求を中断**チェック ボックスをオンにして**OK**します。  

7. **受信パイプライン**、 **AS2EDIReceive**します。  

8. をクリックして**OK**、順にクリックします**OK**もう一度です。  

9. **受信場所**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、受信場所を右クリックし、クリックして**を有効にする**します。  

##### <a name="to-create-a-dynamic-send-port-to-send-the-mdn-to-fabrikam"></a>MDN を Fabrikam に送信するための動的な送信ポートを作成するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**動的な一方向送信ポート**します。  

2. **送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。  

3. **送信パイプライン**、 **AS2Send**します。  

4. コンソール ツリーで、選択**フィルター**します。 **プロパティ**、入力**EdiIntAS.IsAS2AsynchronousMDN**は**演算子**、入力**==**; と**値**、入力**True**します。  

5. **[OK]** をクリックします。  

##### <a name="to-create-a-send-port-to-send-the-edi-payload-to-a-local-folder"></a>EDI ペイロードをローカル フォルダーに送信する送信ポートを作成するには  

1. Windows エクスプ ローラーでという名前の Contoso ローカル フォルダーを作成**EDI_to_Contoso** EDI ペイロードを送信します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  

3. **送信ポートのプロパティ**ダイアログ ボックスで、名前、送信ポートにたとえば、 **Send_Payload**します。 選択**ファイル**の**型**、 をクリックし、**構成**します。  

4. **FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**を参照して選択、 **EDI_to_Contoso**手順 1. で作成したフォルダーにします。 まま**ファイル名**として **%MessageID%.xml**します。 **[OK]** をクリックします。  

5. 既定の**PassThruTransmit**の**送信パイプライン**します。  

6. クリックして**フィルター**コンソール ツリーでします。 **プロパティ**、入力**BTS します。MessageType**します。 **演算子**、入力 **==** します。 **値**、メッセージのメッセージの種類を入力`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`します。  

7. **[OK]** をクリックします。  

8. **送信ポート**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、送信ポートを右クリックし、順にクリックします**開始**します。  

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

1.  右クリック**fabrikam_profile**、 をポイント**新規**、 をクリックし、**契約**します。  

2.  **全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。  

3.  **プロトコル**ドロップダウン リストで、 **AS2**します。  

4.  **2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Contoso**します。  

5.  **2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**します。  

     2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは、一方向の AS2 アグリーメントの構成用です。  

6.  **全般** タブで、**全般プロパティ**ページで、**共通のホスト設定**セクションで、**レポートをオン**します。  

7.  次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。  

    1.  **識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。 **AS2-から**、入力`Fabrikam`します。 **AS2-To**、入力`Contoso`します。  

    2.  **検証** ページで、、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して** チェック ボックス  

    3.  **受信確認 (Mdn)** ページで、次の操作を行います。  

        1.  選択、 **mdn を要求する**チェック ボックスをオンします。  

        2.  必ず、**署名付き MDN を要求**チェック ボックスをオフします。  

        3.  選択、**非同期 MDN を要求する**チェック ボックスをオンします。  

        4.  **- Receipt-delivery-option (URL)** テキスト ボックスに、入力`http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam`します。  

8.  次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。  

    > [!NOTE]
    >  このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。 アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**AS2-から**と**AS2-に**します。  

    1.  **識別子** ページで、値を入力します**AS2-から**と**AS2-に**します。 **AS2-から**、入力`Contoso`します。 **AS2-To**、入力`Fabrikam`します。  

9. **[適用]** をクリックします。  

10. **[OK]** をクリックします。 新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。 新しく追加したアグリーメントは既定で有効になります。  

##### <a name="to-create-an-x12-agreement-between-the-two-business-profiles"></a>2 つのビジネス プロファイルの間に X12 アグリーメントを作成するには  

1. 右クリック**fabrikam_profile**、 をポイント**新規**、 をクリックし、**契約**します。  

2. **全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。  

3. **プロトコル**ドロップダウン リストで、 **X12**します。  

4. **2 番目のパートナー**セクションから、**名前**ドロップダウン リストで、 **Contoso**します。  

5. **2 番目のパートナー**セクションから、**プロファイル**ドロップダウン リストで、 **Contoso_Profile**します。  

    2 つの新しいタブが横に追加の取得と表示されます、**全般**タブ。各タブは一方向 X12 アグリーメントを構成するためのものです。  

6. **全般** タブで、**全般プロパティ**ページで、**共通のホスト設定**セクションで、**レポートをオン**、し、選択**メッセージ ペイロードを格納するレポートの**します。  

7. 次のタスクを実行、 **Fabrikam が Contoso を ->** タブ。  

   1. **識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応しています。  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。 値と一致します**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**をアグリーメントのプロパティと、インターチェンジ ヘッダー。 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。  
      > 
      > [!NOTE]
      >  このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**7654321**、 **ISA7**に**ZZ。**、および**ISA8**に**1234567**します。  

   2. **検証**ページで、**インターチェンジの設定**セクションをご確認ください**重複している isa13 を確認**オプションが選択されていません。  

      > [!NOTE]
      >  オフにすると、**重複している isa13 を確認**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。  

   3. 使用するかどうかに付属する標準スキーマのいずれかの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の**ローカル ホスト設定**ページで、**トランザクション セットの設定**セクションでを使用するスキーマの名前空間を選択します。受信インターチェンジを処理します。  

      |プロパティ|目的|  
      |--------------|----------------|  
      |**[Default]**|列のチェック ボックスをオンにします|  
      |**Target Namespace**|[ `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`] を選択します。|  

      > [!NOTE]
      >  プロパティを設定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、受信 850 インターチェンジの処理に使用するスキーマを決定できるようになります。 グリッド内の行に入力された [GS02] と [ST01] の値がインターチェンジに設定されている場合は、同じ行にあるターゲットの名前空間により、使用するスキーマが決定されます。  

   4. **エンベロープ**ページで、**トランザクション セットの設定**セクションで、次の操作を行います。  


      |       プロパティ       |                                                                                                                                              目的                                                                                                                                               |
      |----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **[Default]**      |              選択**既定**します。 **注:** 既定の値としてこの行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**は使用されている場合であってもの値は、**トランザクションの種類**、**バージョン/リリース**と**ターゲットの名前空間**と一致するメッセージではありません。              |
      | **トランザクションの種類** |                                                                                                          たとえば、テスト メッセージのメッセージの種類を選択**864 – テキスト メッセージ**します。                                                                                                           |
      | **バージョン/リリース**  |                                                                                                                                           入力**00401**します。                                                                                                                                            |
      | **ターゲットの名前空間** |                                                                                                                    選択 **<http://schemas.microsoft.com/BizTalk/EDI/X12/2006>** します。                                                                                                                    |
      |       **[GS1]**        |                                                                                                テスト メッセージのメッセージの種類が選択されているなどを確認します。 **TX - テキスト メッセージ (864)** します。                                                                                                |
      |       **[GS2]**        |                                                                                                                                             入力**01**します。                                                                                                                                             |
      |       **[GS3]**        |                                                                                                                                          入力**7654321**します。                                                                                                                                           |
      |       **GS4**        | 日付の形式を選択します。 選択**CCYYMMDD**します。 **注:** ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。 ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。 |
      |       **GS5**        |                                                                                                                      時刻の形式を選択します。 選択**HHMMSSdd**します。                                                                                                                       |
      |       **GS7**        |                                                                                                                   選択**T - 運輸データ調整委員会 (Tdcc)** します。                                                                                                                   |
      |       **GS8**        |                                                                                                                      EDI のバージョンとして入力されたことを確認します。 **00401**します。                                                                                                                       |


8. 次のタスクを実行、 **Contoso が Fabrikam]-> [** タブ。  

   > [!NOTE]
   >  このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。 アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**します。  

   1.  **識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応しています。  

       > [!NOTE]
       >  このチュートリアルでは、次のように設定します**ISA5**に**ZZ**、 **ISA6**に**1234567**、 **ISA7**に**ZZ。**、および**ISA8**に**7654321**します。  

9. **[適用]** をクリックします。  

10. **[OK]** をクリックします。 新しく追加したアグリーメントが一覧表示、**契約**のセクション、**パーティとビジネス プロファイル**ウィンドウ。 新しく追加したアグリーメントは既定で有効になります。  

### <a name="testing-the-walkthrough"></a>チュートリアルのテスト  
 ここでは、チュートリアルをテストする方法について説明します。  

##### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender フォルダーにある Sender.csproj プロジェクトを開きます。  

2. HttpSender.cs で、次の行がコメント アウトされていないことを確認します (//Request Asynchronous MDN コメント行のすぐ下)。  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864.edi", FileMode.Open, FileAccess.Read);  
   ```  

3. 次の行がコメント アウトされていることを確認します (//Request Synchronous MDN コメント行のすぐ下)。  

   ```  
   Stream sr = new FileStream(getBizTalkInstallPath() + @"SDK\AS2 Tutorial\X12_00401_864-Sync.edi", FileMode.Open, FileAccess.Read);  
   ```  

4. このプロジェクトをビルドします。  

5. Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial に移動します。 メモ帳で X12_00401_864.edi を開きます。 Disposition-Notification-Options ヘッダーを定義している行を削除し、ファイルを保存します。  

6. Windows エクスプ ローラーで、移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 tutorial \sender\bin\debug 実行と**Sender.exe**します。  

   > [!NOTE]
   >  このインスタンスで Sender.exe を実行すると、メッセージ X12_00401_864.edi が Contoso 仮想ディレクトリ (BTS http 受信場所) に送信されます。  

7. 作成した Contoso ローカル フォルダーを開き、EDI ペイロードを (\EDI_to_Contoso) に送信します。 フォルダーに .XML ファイルがあることを確認します。 XML ファイルを開き、そのファイルに 864 トランザクション セットが含まれていることを確認します。  

8. Fabrikam ローカル フォルダーを開きます。MDN はここに返されます。 Windows エクスプ ローラーで、移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_MDNToFabrikam します。 メモ帳でメッセージ ファイルを開き、MDN を確認します。 MDN AS2-From が Contoso で、AS2-To が Fabrikam であることを確認します。  

9. メモ帳でテスト メッセージ X12_00401_864.edi を開き、\EDI_to_Contoso ローカル フォルダー内の出力メッセージのトランザクション セットが、X12_00401_864.edi 入力メッセージのトランザクション セットに対応していることを確認します。  

## <a name="see-also"></a>参照  
 [BizTalk Server AS2 ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)