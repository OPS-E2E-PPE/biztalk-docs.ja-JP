---
title: PeopleSoft Enterprise Sample Get の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb54f14c-3fce-44d6-91bb-cb1ca38a20da
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e4601264b8dc407d1cc1bed323b4d3504bc91d
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753250"
---
# <a name="execute-a-peoplesoft-enterprise-sample-get"></a>PeopleSoft Enterprise Sample Get を実行します。
PeopleSoft システムは、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムから PeopleSoft アダプターを使用してアクセスできます。 このアダプターに含まれている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。
  
 これは PeopleSoft ラボ作業の 2 パート目です。 1 パート目 (ラボ 1) では、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] またはその他の Microsoft テクノロジを使用せずに、PeopleSoft システムに手動でアクセスし、データを変更しました。 このパート (ラボ 2) では、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトの一部として、BizTalk オーケストレーションを作成します。 PeopleSoft アダプターを使用して PeopleSoft システムのデータを取得するために、このオーケストレーションのポートを構成します。  
  
## <a name="prerequisites"></a>前提条件  
  
- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]
  
- Microsoft BizTalk Adapters for Enterprise Applications  
  
- Microsoft Visual Studio  
  
- Sun Systems Java Development Kit (JDK) バージョン 1.4 以降  
  
> [!NOTE]
>  参照してください[をインストールし、エンタープライズ アプリケーション用のアダプターを構成](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)キーの構成については、JD Edwards、PeopleSoft、および TIBCO アダプター。  
  
## <a name="lab-2---executing-a-peoplesoft-sample-get"></a>ラボ 2 - PeopleSoft Sample Get の実行  
 このラボでは、PeopleSoft システムに対して **Get** 操作を実行します。 具体的には、次のタスクを実行します。  
  
- PeopleSoft の前提条件の確認  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] での PeopleSoft 送信ポートのセットアップ  
  
- BizTalk オーケストレーション プロジェクトの作成  
  
- プロジェクトのビルドと展開  
  
- アプリケーションのテストと XML 出力の表示  
  
## <a name="procedures-for-lab-2--executing-a-peoplesoft-sample-get"></a>ラボ 2 の手順 - PeopleSoft Sample Get の実行  
 PeopleSoft システムへのインターフェイス アクセスには、PSJOA.JAR および GET_CI_INFO.PC。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターで、PeopleSoft アダプターは PeopleSoft Java インターフェイスを使用して PeopleSoft システムとやり取りします。 このインターフェイスは PSJOA.JAR ファイルで提供されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に配置されているこのファイルのコピーは、通常、アクセス先の PeopleSoft サーバー システムの管理者から送信されます。 このラボでは、PSJOA.JAR のコピーは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の C:\PSJars\Ver841\ フォルダーにあります。 このファイルの場所は、PeopleSoft アダプター構成プロパティで指定されます。  
  
 PeopleSoft システムには、カスタム コンポーネント インターフェイス (CI) をインストールする必要があります。 インストールすると、アダプターの構成時にアダプターから PeopleSoft オブジェクトを参照できるようになります。 アクセス可能な PeopleSoft オブジェクトのリストを取得するために、カスタム コンポーネント インターフェイスを呼び出します ([生成した項目の追加] 手順から)。 これらのオブジェクトで、クライアント システムから使用できる PeopleSoft の公開機能が決まります。  
  
 具体的には、初期セットアップ時に、カスタム コンポーネント GET_CI_INFO を PeopleSoft システムにインストールする必要があります。 このファイルを変更して、GET_CI_INFO で公開する内容を制限できます (既定では、PeopleSoft システムのすべてのコンポーネント インターフェイスが公開されます)。 ソースは既定で次の場所にある GET_CI_INFO テキスト ファイルです。  
  
 **Enterprise Applications\PeopleSoft Enterprise(r) \Config の C:\Program files \microsoft BizTalk Adapters**  
  
 GET_CI_INFO コンポーネント インターフェイスを PeopleSoft にインストールする方法の一般的な手順が記載[をインストールし、エンタープライズ アプリケーション用のアダプターを構成](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)します。 これらのガイドは、PeopleSoft の操作に慣れた管理者向きです。  
  
## <a name="step-1-confirm-the-peoplesoft-rerequisites"></a>手順 1: PeopleSoft rerequisites を確認します。  
 PeopleSoft アダプターに使用する BizTalk プロジェクトの作成を開始する前に、PeopleSoft へのアクセスに必要な条件がすべてセットアップされていることを確認します。  
  
1. いることを確認、PSJOA します。JAR ファイルに存在する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターの C:\psjars\ver841 フォルダー。 (このファイルは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上では異なる場所にある場合があります。 以下の構成では、ファイルがこの場所にあると想定しています)。  
  
2. C:\Program files \microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r) \Config フォルダーに get_ci_info.pc ファイルが存在することを確認します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。 PeopleSoft アダプターがインストールされ、一覧に表示されていることを確認します。  
  
    PeopleSoft アダプターがインストールされていない場合、BizTalk Adapters for Enterprise Applications をインストールします (前述の「前提条件」の項を参照してください)。 アダプターのインストール後、 **[アダプター]** を右クリックし、 **[新規作成 - アダプター]** をクリックして PeopleSoft アダプターをインストールします。 これを有効にするためにホスト インスタンスを再起動します。  
  
## <a name="step-2-create-a-send-port-for-peoplesoft"></a>手順 2: PeopleSoft の送信ポートを作成します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、PeopleSoft システムとの通信に使用する送信ポートが必要です。 この送信ポートは、最終的にオーケストレーションの論理ポートにバインドされます。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk.EnterpriseApplication します。**  
  
2. **[送信ポート]** を右クリックし、 **[新規作成]** をクリックして、 **[静的な送信請求 - 応答の送信ポート]** を選択します。 **[送信ポートのプロパティ]** ダイアログ ボックスで、プロパティの次の値を入力します。  
  
   1.  **名:**  `PeopleSoftSamplePort`  
  
   2.  **種類:**  `PeopleSoft`  
  
   3.  **送信ハンドラー。**  `BizTalkServerApplication`  
  
   4.  **送信パイプライン。**  `XMLTransmit`  
  
   5.  **受信パイプライン。**  `XMLReceive`  
  
3. **[構成]** をクリックし、次のプロパティ値を入力します。  
  
   1. **[アプリケーション サーバーのパス]**: **//Servername:9000**  
  
       Servername には、使用しているアプリケーション サーバーを指定します。 これは、この PeopleSoft システムの固有のサーバー名または IP アドレスとポート番号です。  
  
   2. **[JAVA_HOME]**: **C:\J2SDK1.4.2_08**  
  
       このパスは、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の Java SDK インストールに固有のパスです。  
  
   3. **パスワード**: \<PeopleSoft パスワードを入力します。\>  
  
   4. **[PeopleSoft 8.x JAR ファイル]**: **C:\PSJARS\VER841\PSJOA.JAR**  
  
   5. **ユーザー名:** \<PeopleSoft UserID を入力します。\>  
  
      ![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")  
  
4. **[OK]** を 2 回クリックしてダイアログ ボックスを閉じます。  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a>手順 3: BizTalk オーケストレーション プロジェクトを作成します。  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で BizTalk プロジェクトを作成し、プロジェクトのオーケストレーションを構成して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と PeopleSoft システム間の通信を処理します。 送信と受信のポートを追加し、プロジェクトをビルドしてから、プロジェクトを展開します。  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を開き、C:\LABS フォルダーに新しい BizTalk プロジェクトを作成します。 **[ファイル]** メニューの **[新規作成]** をクリックします。 **[新しいプロジェクト]** ダイアログ ボックスが表示されます。 **[テンプレート]** セクションで **[空の BizTalk Server プロジェクト]** 入力`PS_Test`クリックと一意のプロジェクトの名前として**OK**。  
  
2. ソリューション エクスプローラーでプロジェクト名を右クリックし、 **[追加]** をクリックし、 **[生成した項目の追加]** をクリックします。 **[カテゴリ]** ペインの **[アダプター メタデータの追加]** を選択し、 **[テンプレート]** 側の **[アダプター メタデータの追加]** を選択し、 **[追加]** をクリックします。  
  
3. アダプターの追加ウィザードで **[PeopleSoft Enterprise]** アダプターを選択し、前の手順で作成した **[PeopleSoftSamplePort]** 送信ポートを選択し、 **[次へ]** をクリックします。  
  
    ![](../core/media/ed0dedc5-a8fb-444c-b884-e310cf56462c.gif "ed0dedc5-a8fb-444c-b884-e310cf56462c")  
  
4. **[インポートするサービスの選択]** ページで、 **[PeopleSoft]**、 **[CI]** の順に展開します。  
  
    PeopleSoft システムは Browsing Agent を使用してアダプターから問い合わせられます。 **[CI]** を展開すると、BrowsingAgent.exe プロセスが開始され (タスク マネージャーで実行中であることを確認できます)、次の図のようにサービスが表示されます。  
  
    ![](../core/media/6988104c-6483-4df2-a637-3301628ea665.gif "6988104c-6483-4df2-a637-3301628ea665")  
  
   > [!NOTE]
   >  PeopleSoft システムから取得されて表示される PeopleSoft サービスは、この図とは一部異なることもあります。  
  
5. スクロールし、 **[LOCATION]** を選択し、 **[完了]** をクリックします。  
  
    ![](../core/media/0506affd-3caa-47cb-9c25-f49c8a0ad614.gif "0506affd-3caa-47cb-9c25-f49c8a0ad614")  
  
6. ソリューション エクスプローラーには、新しい BizTalk オーケストレーションと、2 つの新しい関連スキーマ ファイルが表示されます。 これらのファイルはアダプターの追加ウィザードによって作成されます。 **BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。  
  
    ![](../core/media/825c5690-78eb-4048-9a47-cd3fc7310b7b.gif "825c5690-78eb-4048-9a47-cd3fc7310b7b")  
  
   このオーケストレーションは、入力として、PeopleSoft **Get** メソッド用にフォーマットされた XML ファイルを受け入れ、XML ファイルを PeopleSoft システムに送信します。 **Get** メソッドは、PeopleSoft システムのロケーション情報を取得し、BizTalk オーケストレーションに返します。 オーケストレーションでは、アダプターおよび PeopleSoft システムとのこの通信を容易にするためにポートが使用されます。 ここで構成するポートは、XML ファイルの送受信用です。 送信 XML ファイルは、これが **Get** 操作であることを PeopleSoft システムに示します。 受信 XML ファイルは、オーケストレーションに場所情報を返します。  
  
   オーケストレーションを完成させるには、XML の送信と受信のためのポートを作成および構成する必要があります。 まず、 **Get** メソッドを含む最初の XML 入力ファイルを受け入れてオーケストレーションを開始できるように、新しい受信ポートをセットアップします。  
  
#### <a name="configure-a-receive-port"></a>受信ポートを構成します。  
  
1. 前の手順で開いた BizTalk Orchestration.odx ファイル内で、左のポート画面を右クリックし、 **[新しい構成済みのポート]** をクリックします。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。  
  
2. **ポートのプロパティ**ページで、入力`FileIn`の**名前**、順にクリックします**次**。  
  
3. **[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]** を選択し、次のプロパティ値を入力または選択します。  
  
    **ポートの種類名**: `FileInPort`  
  
    **[通信方式]**: **一方向**  
  
    **[アクセスの制限]**: **[内部 - このプロジェクト限定]**  
  
4. **[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。  
  
    **[ポートの通信方向]**: **常にこのポートでメッセージを受信する**  
  
    **[ポートのバインド]**: **[後で指定する]**  
  
5. **[次へ]** をクリックし、 **[完了]** をクリックします。 このファイルをディスクからの入力として受け入れるには、ファイル アダプターを使用します。  
  
   次に、PeopleSoft **Get** メソッドに対する呼び出しからの場所の結果を含む XML ファイルを受け入れる送信ポートを作成します。 オーケストレーションでは、この送信ポートを介してディスクにこの XML ファイルを書き込むためにファイル アダプターを使用します。  
  
#### <a name="configure-a-send-port"></a>送信ポートを構成します。  
  
1. BizTalk Orchestration.odx ファイルで、左のポート画面を右クリックし、 **[新しい構成済みのポート]** をクリックします。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。  
  
2. **ポートのプロパティ**ページで、入力`FileOut`の**名前**、順にクリックします**次**。  
  
3. **[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]** を選択し、次のプロパティ値を入力または選択します。  
  
    **ポートの種類名**: `FileOutPort`  
  
    **[通信方式]**: **一方向**  
  
    **[アクセスの制限]**: **[内部 - このプロジェクト限定]**  
  
4. **[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。  
  
    **[ポートの通信方向]**: **[常にこのポートでメッセージを送信する]**  
  
    **[ポートのバインド]**: **[後で指定する]**  
  
5. **[次へ]** をクリックし、 **[完了]** をクリックします。  
  
   最後に、PeopleSoft システムに対する **Get** メソッドを含む最初の XML 入力ファイルを送信するために、送信/受信ポートを作成します。 また、このポートは、PeopleSoft システムでの **Get** メソッドの呼び出し結果である場所情報を含む XML ファイルも受信します。  
  
#### <a name="configure-a-sendreceive-port"></a>送信/受信ポートを構成します。  
  
1. BizTalk Orchestration.odx ファイルで、右のポート画面を右クリックし、 **[新しい構成済みのポート]** をクリックします。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。  
  
2. **ポートのプロパティ**ページで、入力`PeopleSoft_Port`の**名前**、順にクリックします**次**。  
  
3. **[ポートの種類の選択]** ページで、 **[既存のポートの種類を使用する]** をクリックします。 **[利用可能なポートの種類]** について **[PS_Test.LOCATION]** を選択し、 **[次へ]** をクリックします。  
  
    ![](../core/media/d8b443ec-294d-4124-a29d-aeb42bbb107e.gif "d8b443ec-294d-4124-a29d-aeb42bbb107e")  
  
4. **[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。  
  
    **[ポートの通信方向]**: **[常に要求を送信し、応答を受信します。]**  
  
    **[ポートのバインド]**: **[後で指定する]**  
  
5. **[次へ]** をクリックし、 **[完了]** をクリックします。  
  
   ポート画面には、PeopleSoft Location サービスの新しいポートと使用できるメソッドが表示されます。 後で、PeopleSoft システムからファイルを送受信する PeopleSoft アダプターを指定します。  
  
   ここでは、2 つの **送信** 図形と 2 つの **受信** 図形をオーケストレーションに挿入し、作成したポートにリンクします。  
  
#### <a name="add-send-and-receive-shapes"></a>追加の送信と受信図形  
  
1. ツールボックスから **受信** コンポーネントをドラッグし、オーケストレーション (緑色の円) の先頭の真下にドロップします。 をクリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`FromDisk`の、**名前**、設定と**アクティブ化**に`true`します。 このように設定すると、この受信ポートでドキュメントを受信したときにオーケストレーションがアクティブになります。  
  
2. ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **FromDiskReceive**図形。 [新規] をクリックして**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`ToPS`の、**名前**します。  
  
3. ドラッグ、**受信**コンポーネントをツールボックスからすぐ下にドロップし、 **To_PS**<strong>送信</strong>図形。 をクリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`FromPS`の、**名前**します。  
  
4. ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **From_PSReceive**図形。 [新規] をクリックして**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`ToDisk`の、**名前**します。  
  
   これらの図形を論理ポートに接続するには、処理するメッセージの種類を定義する必要があります。 アダプターには受信 (**Request** メソッド) メッセージおよび送信 (**Response** メソッド) メッセージの両方が必要です。 各メソッドのメッセージは異なります。  
  
   このオーケストレーションでは、 **Get-Request** メッセージと **Get-Response** メッセージのみを使用しています。 オーケストレーションが (たとえば **UpdateEx** メソッドを使用して) データを更新する場合、別の Request/Response メッセージが必要です。  
  
#### <a name="define-and-assign-messages-to-ports"></a>定義し、メッセージをポートに割り当てる  
  
1.  左のポート画面で、 **[FileIn]** ポートの **[Request]** をクリックします。 [プロパティ] ウィンドウで、 **[メッセージの種類]**、 **[マルチパート メッセージ]** の順に展開し、 **[PS_Test.Get]** をクリックします。  
  
2.  左のポート画面で、 **[FileOut]** ポートの **[Request]** をクリックします。 [プロパティ] ウィンドウで、 **[メッセージの種類]**、 **[マルチパート メッセージ]** の順に展開し、 **[PS_Test.GetResponse]** をクリックします。  
  
     ![](../core/media/6b844ca3-322a-47b3-8cfd-68652c950752.gif "6b844ca3-322a-47b3-8cfd-68652c950752")  
  
3.  **[FileIn]** ポートを選択し、外向きの送信の矢印を **[FromDisk]** 図形の内向きの受信の矢印にドラッグします。  
  
4.  **[FileOut]** ポートを選択し、内向きの受信の矢印を **[ToDisk]** 図形の外向きの送信の矢印にドラッグします。  
  
5.  優れたアプリケーションの設計原則に従って、既存の汎用メッセージ名をよりわかりやすい名前に変更します。 ソリューション エクスプローラーで、 **[オーケストレーションの種類]** タブをクリックします。[メッセージ]の下にある **[Message_1]** の識別子を **[PS_Msg]** に変更します。 **[Message_2]** の識別子を **[PS_Resp]** に変更します。  
  
     ![](../core/media/5ec92b81-4a55-4d44-a360-78a6aaa64255.gif "5ec92b81-4a55-4d44-a360-78a6aaa64255")  
  
     ![](../core/media/04b31c26-73a6-40a6-8d50-39c7c929d6a1.gif "04b31c26-73a6-40a6-8d50-39c7c929d6a1")  
  
6.  **[To_PS]** 送信図形を選択し、 **[Message]** プロパティを **[PS_Msg]** に設定します。  
  
7.  **[From_PS]** 受信図形を選択し、 **[Message]** プロパティを **[PS_Resp]** に設定します。  
  
8.  **[To_PS]** 送信図形を、 **[PeopleSoft_Port]** ポートの **[Get]** メソッドの **[Request]** 部分に接続します。  
  
9. **[From_PS]** 送信図形を、 **[PeopleSoft_Port]** ポートの **[Get]** メソッドの **[Response]** 部分に接続します。  
  
     ![](../core/media/d16e02bc-954c-4aa2-99d6-3fee1222c730.gif "d16e02bc-954c-4aa2-99d6-3fee1222c730")  
  
## <a name="step-4-build-and-deploy-the-project"></a>手順 4: 構築し、プロジェクトの配置  
 BizTalk プロジェクトが完成したので、ビルドし、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に展開できます。  
  
1.  Visual Studio で、] をポイント**Visual Studio Tools**、し、[ **Visual Studio コマンド プロンプト**します。  
  
2.  プロジェクトをビルドするには、厳密な名前キーファイルが必要です。コマンド プロンプトに次のように入力し、厳密な名前のキー ファイルを作成します。  
  
     **sn-k labs.snk**  
  
3.  ソリューション エクスプローラーで、 **[PS_Test]** プロジェクトを右クリックし、 **[プロパティ]** をクリックして、プロジェクトのプロジェクト デザイナーを起動します。  
  
4.  **[署名]** タブをクリックします。  
  
5.  **[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]** をクリックします。  
  
6.  キー ファイル **labs.snk**を一覧から選択して **[開く]** をクリックします。  
  
7.  プロジェクト デザイナーの **[展開]** タブをクリックします。  
  
8.  設定、**アプリケーション名**に`PS_Test`します。  
  
9. ソリューション エクスプローラーで **[PS_Test]** プロジェクトを右クリックし、 **[ビルド]** をクリックします。  
  
10. ビルドが正常に完了したら、 **[PS_Test]** プロジェクトを右クリックし、 **[展開]** をクリックします。  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a>手順 5: テスト、アプリケーションと XML 出力を表示します。  
 次に、作成して展開したアプリケーションをテストします。 初めに、オーケストレーション プロセスを開始する XML ファイルを作成します。次に、アプリケーション内で XML ファイルを送受信するためのフォルダーを構成します。 アプリケーションの構成後は、アプリケーションを実行し、オーケストレーションが返す XML ファイルを表示します。  
  
#### <a name="generate-the-xml-file-for-the-query"></a>クエリの XML ファイルを生成します。  
  
1.  ソリューション エクスプローラーで、 **LOCATIONService_LOCATION_x5d.xsd** をクリックしてファイルを開きます。  
  
2.  **LOCATIONService_LOCATION_x5d.xsd** を右クリックし、 **[プロパティ]** をクリックします。 **[出力インスタンス ファイル名]** に、サンプル XML のパスとファイル名を次のとおりに入力します。  
  
     `C:\LABS\PS_TEST\SAMPLEQUERY.XML`  
  
3.  **[OK]** をクリックします。 [プロパティ] ウィンドウで次のように選択します。 **\<スキーマ\>** 設定と**ルート参照: 取得**します。  
  
4.  **LOCATIONService_LOCATION_x5d.xsd** を右クリックし、 **[インスタンスの生成]** をクリックします。 **SampleQuery.xml** ファイルが生成されます。 このファイルは、オーケストレーション プロセスを開始するアダプターに対する入力として、受信場所にドロップされます。  
  
     ![](../core/media/ef65a96c-2daa-44db-ab95-d18b1fda934e.gif "ef65a96c-2daa-44db-ab95-d18b1fda934e")  
  
#### <a name="configure-and-start-the-biztalk-application"></a>構成し、BizTalk アプリケーションを起動  
  
1. 入力ファイルの受信と送出ファイルの送信のフォルダーを構成します。 移動して**C:\LABS\PS_TEST**という 2 つの新しいサブフォルダーを作成および`FileIn`と`FileOut`します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[**コンソール ルート**、展開**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、展開**BizTalk グループ**、展開**アプリケーション**、右クリックして **[ps_test]** ] をクリックし、**構成**します。  
  
    ![](../core/media/e45f4c8b-fc8a-492a-9824-5232eb728d95.gif "e45f4c8b-fc8a-492a-9824-5232eb728d95")  
  
3. **[Orchestration_1]** を選択し、 **[ホスト]** ドロップダウン ボックスをクリックします。 **[BizTalkServerApplication]** を選択します。  
  
4. [**受信ポート**、] をクリックして **\<None\>** します。 ドロップダウン リストの **[新しい受信ポート]** を選択します。  
  
5. **名前**、型`FileInPort`、順にクリックします**OK**します。 受信場所を指定する必要があるというメッセージ ボックスが表示されます。 **[OK]** をクリックし、 **[新規作成]** をクリックします。  
  
    ![](../core/media/298638b6-0eb8-49c4-8a2e-485571d070cf.gif "298638b6-0eb8-49c4-8a2e-485571d070cf")  
  
6. プロパティに次の値を入力または選択します。  
  
    **名前**: `FileInLoc`  
  
    **種類**: **ファイル**  
  
    **受信ハンドラー**: **BizTalkServerApplication**  
  
    **受信パイプライン**: **XMLReceive**  
  
    ![](../core/media/613a5dbc-effe-4827-a72b-d16eef8d0e8a.gif "613a5dbc-effe-4827-a72b-d16eef8d0e8a")  
  
7. **[構成]** をクリックし、 `C:\LABS\PS_TEST\FILEIN` に「 **C:\LABS\PS_TEST\FILEIN**の順にポイントし、 **[OK]** を 3 回クリックします。  
  
    ![](../core/media/513eebb0-58ca-4aaa-a33b-31700f9cf7a8.gif "513eebb0-58ca-4aaa-a33b-31700f9cf7a8")  
  
8. クリックして**\<None\>** の**PeopleSoft_Port**ドロップダウン リストでします。  
  
9. **[新しい送信ポート]** を選択し、プロパティに次の値を選択または入力します。  
  
     **名前**: `PS_Test_Port`  
  
     **種類**: **PeopleSoft**  
  
     **[送信ハンドラー]**: **BizTalkServerApplication**  
  
     **[パイプライン]**: **XMLTransmit** および **XMLReceive**  
  
10. **[構成]** をクリックし、次のプロパティ値を入力します。  
  
    1. **[アプリケーション サーバーのパス]**: **//Servername:9000**  
  
        Servername には、使用しているアプリケーション サーバーを指定します。 これは、この PeopleSoft システムの固有のサーバー名または IP アドレスとポート番号です。  
  
    2. **[JAVA_HOME]**: **C:\J2SDK1.4.2_08**  
  
        このパスは、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の Java SDK インストールに固有のパスです。  
  
    3. **パスワード**: \<PeopleSoft パスワードを入力します。\>  
  
    4. **[PeopleSoft 8.x JAR ファイル]**: **C:\PSJARS\VER841\PSJOA.JAR**  
  
       **ユーザー名:** \<PeopleSoft UserID を入力します。\>  
  
11. **[OK]** を 2 回クリックしてダイアログ ボックスを閉じます。  
  
12. 構成 Applicationwindow で、クリックして**\<None\>** の**FileOut**ドロップダウン リストでします。  
  
13. **[新しい送信ポート]** を選択し、プロパティの値を次のとおりに入力または選択します。  
  
     **名前**: `FileOutPort`  
  
     **種類**: **ファイル**  
  
     **[送信ハンドラー]**: **BizTalkServerApplication**  
  
     **送信パイプライン**: **XMLTransmit**  
  
14. **[構成]** をクリックし、`C:\Labs\PS_Test\FileOut` に「 **C:\Labs\PS_Test\FileOut** 」と入力します。 **[ファイル名]** に「 **%MessageID%.xml** because this results in a unique file に「 each message.  
  
15. **[OK]** を 3 回クリックして、ダイアログ ボックスを閉じます。  
  
16. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして、 **[ps_test]** アプリケーションをクリック**開始**します。  
  
     ![](../core/media/7bf30707-c7c6-409f-af18-9c9dfeb0de58.gif "7bf30707-c7c6-409f-af18-9c9dfeb0de58")  
  
#### <a name="test-the-orchestration"></a>オーケストレーションをテストします。  
  
1.  **C:\Labs\PS_Test** ディレクトリの **Samplequery.xml** ファイルを次のように変更します。  
  
    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
      <ns0:SETID>SHARE</ns0:SETID>  
      <ns0:LOCATION>AUS01</ns0:LOCATION>  
      <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  
  
    > [!NOTE]
    >  **SHARE** データ値はすべてのシステムで使用されます。 ただし、この XML ファイルの **Location** に使用される値は、実際のシステムに存在する必要があります。 これはラボ 1 で確認しました。  
  
2.  変更内容を保存し、ファイルを **C:\Labs\PS_Test\FileIn** フォルダーにコピーします。 これは、オーケストレーション プロセスが開始される FileIn の受信場所です。  
  
3.  数秒後に、XML ファイルが **C:\Labs\PS_Test\FileOut** フォルダーに表示されます。 このファイルには、場所が AUS01 であるレコードのデータが含まれます。  
  
     ![](../core/media/1320ea3c-b2bc-4717-b200-c3c550079ccb.gif "1320ea3c-b2bc-4717-b200-c3c550079ccb")  
  
     この返されたレコード データは、PeopleSoft ラボ 1 での PeopleSoft システムに対するクエリで返された内容と一致する必要があります。 値を比較することで取得したラボ 1 で具体的には、 **Address1**と**住所 2**に、ここで表示される内容を行、 **\<場所: ADDRESS1\>** と**\<場所: 住所 2\>** フィールド、ことを確認することができます、**取得**メソッドが正常に動作します。  
  
## <a name="summary"></a>まとめ  
 このラボでは、PeopleSoft システムにアクセスするための前提条件が適切にセットアップされていることを最初に確認しました。 次に、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、オーケストレーションが含まれる新しい BizTalk プロジェクトを作成しました。 また、BizTalk オーケストレーションを構成し、PeopleSoft アダプターを使用して PeopleSoft システムのデータを取得しました。 オーケストレーションを構成するために、送信ポート、受信ポート、および送信/受信ポートを作成しました。 これらのポートを PeopleSoft アダプターにバインドし、メッセージを適切なポートに割り当てました。  
  
 BizTalk プロジェクトの作成後、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してプロジェクトをビルドして展開しました。 次に、新しいアプリケーションを構成し、実行して PeopleSoft システムのデータを取得しました。 アプリケーションが適切に動作していることを確認するために、出力 XML ファイルを、ラボ 1 で PeopleSoft システムから受信したファイルと比較しました。