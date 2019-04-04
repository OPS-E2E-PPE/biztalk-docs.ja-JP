---
title: 構成 FileAct および InterAct アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d3876ff-e8e4-47f4-9ca8-d4dad419ed67
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d62e4cf0896e755a0ec8ece00d6a2140210b463
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974603"
---
# <a name="configure-the-fileact-and-interact-adapter"></a>構成 FileAct および InterAct アダプター
使用されるさまざまな成果物を構成、[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]ランタイム。 

  
## <a name="prerequisites"></a>前提条件  
   
- インストールします [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]
  
- メンバーとしてサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループ
  
- SQL Server が実行されていることを確認します。
  
## <a name="step-1-configure-the-fileact-and-interact-adapter"></a>手順 1: FileAct および InterAct アダプターを構成します。  
  
1.  **Microsoft BizTalk FileAct と対話するアダプターの構成**ウィザードに移動して**概要**します。 左側のウィンドウで次のように選択します。**ランタイム**アダプターのランタイム コンポーネントを構成します。  
  
2.  **のランタイム構成** **アカウント**COM + ストア アンド フォワード モードの構成を入力する省略記号 [...] を選択します。  
  
3.  **ユーザーの資格情報**、ユーザー名を入力します (で、 *domain \user name*形式) と COM + の構成で使用するアカウントのパスワード。 **[OK]** を選択します。  
  
    > [!NOTE]
    >  A**ユーザーの資格情報**入力したアカウントに推奨されるよりも高い特権がある場合に警告が表示されます。 選択**はい**を続行します。
  
4.  選択**構成の適用**FileAct と対話するアダプターに COM + 構成を適用します。  
  
5.  **概要**、レビュー、および選択**次**します。  
  
6.  構成が完了したら、コンポーネントの一覧を確認します。 チェック マークは、コンポーネントが正常に構成されていることを意味します。 "X"は、そのコンポーネントに問題があることを意味します。  
  
    > [!NOTE]
    >  使用して、 **Logfile**構成イベントを表示するリンク。  
  
7.  選択**完了**構成を完了します。 **概要**ランタイム コンポーネントの現在の構成状態が表示されます。  

次に、これらのアダプターを実行するには、ホストとホスト インスタンスを作成します。

## <a name="step-2-create-the-host-and-host-instances"></a>手順 2: ホストとホスト インスタンスを作成します。

FileAct アダプターの専用ホストと InterAct アダプターの個別の専用ホストを作成することをお勧めします。 アダプターごとに少なくとも 1 つのホスト インスタンスを作成します。  

[BizTalk ホストとホスト インスタンスを管理する](../../core/managing-biztalk-hosts-and-host-instances.md)ホストとホスト インスタンスを作成する手順を一覧表示します。 

作成されたら、次の手順は、送信ハンドラーを追加し、SWIFT Alliance ゲートウェイ (SAG) で作成したクライアントのメッセージのパートナーを使用するがします。

## <a name="step-3-create-the-send-handler"></a>手順 3: 送信ハンドラーを作成します。

FileAct および InterAct ハンドラーのプロパティとして送信、送信ポートの構成値、個々 の FileAct プロパティが設定されていないか InterAct 送信ポートします。 
  
1. **BizTalk Server 管理**コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。  
  
2. 選択、 **FileAct**または**InterAct**アダプター。 右側のウィンドウで、送信ハンドラをダブルクリックします。  
  
3. **ホスト名**ドロップダウン リストで、前のセクションで作成したホストを選択します。 選び**プロパティ**します。  
  
4. **トランスポートのプロパティ**を選択、**引数**プロパティとしては、次の引数を入力します。  
  
    `-SagMessagePartner <Client Message Partner created in SAG\>`
  
   > [!NOTE]
   >  置換 <`Client Message Partner created in SAG`> クライアント メッセージのパートナーの名前に置き換えます。 暗号モード、FACrypto モード、およびしプロパティの既定値のままにします。  
  
5. 選択 **[ok]** 変更を保存し、[プロパティ] ウィンドウを閉じます。 
  
6. **プラットフォームの設定**、**ホスト インスタンス**します。  
  
7. ホスト インスタンスを再起動します。 

   - FileAct のホスト インスタンスを右クリックし、**再起動**
   - InterAct のホスト インスタンスを右クリックし、**再起動**します。  

次に、SWIFTNet に paramfile に FileAct を有効にする、サーバー メッセージ パートナーを入力し、InterAct アダプターの受信します。
  
## <a name="step-4-configure-the-swiftnet-param-file"></a>手順 4: SWIFTNet param ファイルを構成します。

有効にするには、FileAct および InterAct アダプターは SWIFTNet に paramfile に入力する必要があります SAG で作成したパートナー サーバーのメッセージの値で初期化するためを受信します。 Paramfile に通常格納されて`c:\SWIFTAlliance\RA\<remote access instance name\>\cfg\paramfile`します。 開始する前に paramfile を構成する**SnlReceiver.exe**します。  
  
1. 開く、 **SWIFTNet に paramfile**します。 マークされた場所に"***"、以下を追加します。 なお、`AdapterType`値を指定できます`Interact`または`Fileact`します。  
  
     ```spawn "snlreceiver -SagMessagePartner <Server MessagePartnerName\> -AdapterMode <AdapterType\>"```  
       
  
   ```  
    username:snlowner  
    subsystem_name:SampleSubsystem  
    #subsystem_group: SampleSubsystem  
    #subsystem_dependency:Support,Swarm  
    subsystem_nature:critical  
    subsystem_start:  
    ***  
    *END  
    subsystem_stop:  
    *KILL9:snlreceiver  
    *END  
    subsystem_status:  
    *NB:1:snlreceiver  
    *END  
    start_event:SNL001:subsystem SampleSubsystem is up  
    stop_event:SNL002:subsystem SampleSubsystem is down  
   ```  
  
> [!NOTE]
>  SNLreceiver を開始する前に、受信ポートを有効にする (FileAct または対話) を使用するアダプター。  
  
2. 開始および停止 SnlReceiver.exe:

    1.  デスクトップで、選択、**リモート API**リモート API のコマンド プロンプトを開くにはアイコン。  
  
    2.  コマンド プロンプトで「`Swiftnet start`します。 SnlReceiver.exe を開始するには ENTER を選択します。  
  
    3.  コマンド プロンプトで「`Swiftnet stop`します。 SnlReceiver.exe を停止するには ENTER を選択します。  

  
次に、ファイルを更新**autoexec.bat** SWIFT 環境変数を設定します。

## <a name="step-5-update-autoexecbat-to-configure-the-receive-adapters"></a>手順 5: 更新プログラムの autoexec.bat 受信アダプタを構成するには

更新プログラム、 **autoexec.bat**をインストールしたコンピューターで、SWIFT 環境変数を設定するファイル、[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]受信アダプター。 環境変数は、パスにインストールされている受信アダプターがあるシステムから生成される`c:\SWIFTAlliance`という名前の受信アダプターのインスタンスと**Ra1**します。 適切に構成の SWIFT 環境変数を更新します。  
  
 Autoexe.bat ファイルのサンプルを次に示します。
  
```  
SET COMPUTERNAME=<Machine Name>  
SET GENLOG_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET GENUTIL_DIR=C:\SWIFTAlliance\RA\bin  
SET HOMEDRIVE=C:  
SET LOGONSERVER=\\SERVERNAME  
SET OSA_DIR=C:\SWIFTAlliance\RA\Ra1\log  
SET OSA_INSTANCE=Ra1  
SET PKIEXECDIR=C:\SWIFTAlliance\RA  
SET SAGRA_HOME=C:\SWIFTAlliance\RA  
SET SESSIONNAME=RDP-Tcp#1  
SET SLP_ENV=DEFAULT  
SET SLP_FILE=server.slp  
SET SNL_DOMAIN_NAME=Ra1  
SET SPK_DATA_DIR=C:\SWIFTAlliance\RA\data\pki  
SET SWNET_BIN_PATH=C:\SWIFTAlliance\RA\Ra1\bin  
SET SWNET_CFG_PATH=C:\SWIFTAlliance\RA\Ra1\cfg  
SET SWNET_HOME=C:\SWIFTAlliance\RA  
SET SWNET_HOST=HOSTNAME  
SET SWNET_INST=Ra1  
SET SWNET_LOG_PATH=C:\SWIFTAlliance\RA\Ra1\log  
SET SWNET_SLP_PATH=C:\SWIFTAlliance\RA\data\  
SET SWNET_VERSION=5.0.20  
SET SWTRACE=C:\SWIFTAlliance\RA\Ra1\log  
SET Path=%PATH%;C:\SWIFTAlliance\RA\bin  
SET Path=%PATH%;C:\SWIFTAlliance\RA\lib  
  
```  
  
## <a name="see-some-examples"></a>いくつかの例を参照してください。
FileAct および InterAct メッセージの例については、[サンプルを操作および FileAct メッセージ](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)を参照してください。  
  
## <a name="see-also"></a>参照  

[FileAct および InterAct アダプターをインストールする](../../adapters-and-accelerators/fileact-interact/install-the-fileact-and-interact-adapter.md)  
[FileAct および InterAct アダプターをアンインストールまたは修復する](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[インストールに関する既知の問題の確認](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
