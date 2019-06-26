---
title: ファイル アダプター (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, File adapters
- File adapters, examples
ms.assetid: d59cecb4-6353-44d5-b8d6-316446758536
caps.latest.revision: 46
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2260c29394227c9bcd905f0b87b062a35ee27e1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345570"
---
# <a name="file-adapter-biztalk-server-sample"></a>ファイル アダプター (BizTalk Server サンプル)
ファイル アダプター サンプルは、Microsoft BizTalk Server を使用する .NET Microsoft Visual c# で記述されます。 動的または静的アダプターのいずれかをビルドするコードを提供します。  ただし、次の手順では、静的アダプターのみについて説明します。 静的アダプターとは、静的な一連のスキーマとカスタム ユーザー インターフェイスのないアダプターです。 動的アダプターには、カスタム ユーザー インターフェイスと可能性のあるスキーマの動的なセットがあります。 静的および動的アダプターでは、アダプターの追加ウィザードを使用して、そのスキーマを BizTalk プロジェクトに追加します。  

> [!NOTE]
>  ファイル アダプター サンプルは、BizTalk Server に付属のネイティブ ファイル アダプターと同じではありません。 そのためこのサンプルを使用して、トランスポートの種類を選択すると選択とファイルではなく「静的」です。  

 動的アダプターのカスタム ユーザー インターフェイスとスキーマの可能性のある動的なセットとは、アダプター管理側でコードを追加で必要があります。 動的スキーマのセットの使用をより深く理解するを参照してください。[動的デザイン時アダプター構成](../core/dynamic-design-time-adapter-configuration.md)します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 サンプル アダプターがファイル フォルダーからファイルをコピーし、メッセージとして BizTalk に送信またはからメッセージを受け取り[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ファイル フォルダーにドロップします。 動的または静的アダプター; のいずれかをビルドするコードを提供しますただし、次の手順では、静的アダプターのみについて説明します。 静的アダプターとは、静的な一連のスキーマとカスタム ユーザー インターフェイスのないアダプターです。 動的アダプターには、カスタム ユーザー インターフェイスと可能性のあるスキーマの動的なセットがあります。 静的および動的アダプターでは、アダプターの追加ウィザードを使用して、そのスキーマを BizTalk プロジェクトに追加します。  

 サンプル ファイル アダプターは、他のカスタム アダプターを作成するテンプレートとして使用できます。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\> **\AdaptersDevelopment\File アダプター**  

> [!NOTE]
>  既定の場所\<*サンプル パス*\>は *%programfiles%* \Microsoft BizTalk Server\SDK\Samples 32 ビットを実行するコンピューターで BizTalk Server がインストールされている場合Windows のバージョンです。 既定の場所\<*サンプル パス*\>は *%programfiles (x86) %* \Microsoft BizTalk Server\SDK\Samples 64 を実行するコンピューターに BizTalk Server がインストールされている場合Windows のビットのバージョンです。 関連付けられている値を決定する、 *%programfiles%* または *%programfiles (x86) %* 環境変数の型**echo %programfiles%** または**echo %%Programfiles (x86) %** コマンド プロンプトで ENTER キーを押します。 このサンプルを 64 ビットのオペレーティング システムを実行から .reg ファイルのいずれかのすべての参照を変更する必要があります **%programfiles%** に **%programfiles (x86) %** .reg ファイルを実行する前にします。  

 次の表では、このサンプルでは、ファイルを表示して、その目的を説明します。  

|\File adapter のファイル|説明|  
|--------------------------|-----------------|  
|\BizTalk project のファイル|サンプル アダプターをテストするため、アダプター ハーネス プロジェクトが含まれています。|  
|\Design time のファイル|デザイン時および管理プロジェクト (AdapterManagement.csproj) が含まれています。|  
|\Runtime files|実行時のファイル コピーを含む受信および送信プロジェクト (DotNetFile.csproj)。|  
|DynamicAdapterManagement.reg|サンプルの動的アダプターを登録します。|  
|Instance.xml|ファイル アダプターを通過するサンプル ファイルです。|  
|StaticAdapterManagement.reg|サンプルの静的アダプターを登録します。|  

|\BizTalk Project\Adapter harness のファイル|説明|  
|----------------------------------------------|-----------------|  
|AdapterHarness.odx, AdapterHarness.sln, AdapterHarnessProject.btproj|プロジェクト、ソリューション、および BizTalk プロジェクトの他の関連ファイルを提供します。|  
|mySchema.xsd|オーケストレーションによって、アダプターの送信部分に渡される Instance.xml のスキーマと同様に、アダプターの受信部分からのハーネス オーケストレーションで想定される Instance.xml スキーマを提供します。|  

|\Design Time\Adapter Management files|説明|  
|---------------------------------------------|-----------------|  
|AdapterManagement.cs、AdapterManagement.csproj、AdapterManagement.sln|プロジェクト、ソリューション、およびアダプターのデザイン時の関連ファイルです。|  
|AssemblyInfo.cs|このサンプルのアセンブリ情報が含まれています。|  
|CategorySchema2.xml|サンプル アダプターによって使用されません。|  
|CategorySchema.xml|静的アダプターのサービス組織ツリーが含まれています。|  
|DotNetFileResource.resx|リソースが含まれています。|  
|ReceiveHandler.xsd、ReceiveLocation.xsd|含む受信側のハンドラーおよびエンドポイントのカスタム プロパティ スキーマ|  
|service1.wsdl|アダプターの操作の定義が含まれています。|  
|TransmitHandler.xsd, TransmitLocation.xsd|含む送信側のハンドラーおよびエンドポイントのカスタム プロパティ スキーマ|  

|                                                                                                                                                             \Runtime files                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DotNetFile.csproj, DotNetFile.sln,<br /><br /> AssemblyInfo.cs、<br /><br /> DotNetFileExceptions.cs、DotNetFileProperties.cs、DotNetFileReceiver.cs、DotNetFileReceiverEndPoint.cs、DotNetFileTransmitter.cs、<br /><br /> DotNetFileTransmitterEndpoint.cs、<br /><br /> DotNetFileAsyncTransmitterBatch.cs,<br /><br /> BatchMessage.cs | 実行時のファイル コピーのファイルは、送信および受信アダプター。 変更して、カスタム コンポーネントの新しい名前でこれらのファイルを保存できます。<br /><br /> DotNetFile.csproj と DotNetFile.sln は、プロジェクトとソリューション ファイルです。<br /><br /> AssemblyInfo.cs には、このサンプルのアセンブリ情報が含まれています。<br /><br /> DotNetFileReceiver.cs は受信場所から、ファイルを読み取りおよびに送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。<br /><br /> メッセージの処理中に例外を処理する DotNetFileExceptions.cs,implements コード<br /><br /> DotNetFileProperties.cs には、受信と送信の両方の操作の一般的なプロパティが含まれています。<br /><br /> BatchMessage.cs は、バッチのメッセージングを実装します。<br /><br /> DotNetFileReceiverEndPoint.cs は、対応するクラスを受信場所/URI します。  新しいメッセージの特定のフォルダーのポーリングを処理します。<br /><br /> DotNetFileTransmitter.cs は、DotNetFile 送信アダプターの単一クラスです。 このアダプターの種類のさまざまな送信ポートをすべてのメッセージがこのクラスを経由します。<br /><br /> DotNetFileTransmitterEndpoint.cs,handles メッセージを転送します。 |

|\SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2 files|説明|  
|--------------------------------------------------------------------|-----------------|  
|Adapter.cs、AdapterException.cs、AsyncTransmitter.cs、batch.cs、ConfigProperties.cs、ControlledTermination.cs、IManageEndpoints.cs、Receiver.cs、ReceiverEndpoint.cs|ベース アダプターを構成するクラスを提供します。 これらを使用するには、独自のアダプターを作成します。|  

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 その他のカスタム アダプターを作成するテンプレートとしてサンプル ファイル アダプターを使用します。  

## <a name="building-this-sample"></a>このサンプルのビルド  

> [!IMPORTANT]
>  BizTalk のインストールが 64 ビット、またはインストールの場所が変更された、OutboundAssemblyPath、InboundAssemblyPath、AdapterMgmtAssemblyPath しなければ適切に変更します。  

 次の手順を使用して、ビルドして、ファイル アダプタのサンプルを初期化します。  

#### <a name="to-create-a-strong-name-key-for-the-dotnetfileadapter-projects-and-the-base-adapter-project"></a>DotNetFileAdapter プロジェクトおよびベース アダプター プロジェクトの厳密な名前キーを作成するには  

1.  開始**Visual Studio コマンド プロンプト**します。  

    > [!NOTE]
    >  コマンド プロンプトを管理者として実行します。  

2.  現在のディレクトリを変更、 \<*サンプル パス*\> **\AdaptersDevelopment\BaseAdapter\v1.0.2**ディレクトリ。  

3.  コマンド プロンプトで「 **sn – k BaseAdapter.snk**し、ENTER キーを押します。 以前に実行されているその他のサンプルの結果としてこの .snk ファイルが既にあります。 そうである場合、手順 4 と、この手順をスキップする権利を移動できます。  

4.  現在のディレクトリを変更、 \<*サンプル パス*\>\\**AdaptersDevelopment\File Adapter\Runtime**ディレクトリ。  

5.  コマンド プロンプトで「 **sn – k DotNetFileAdapter.snk**し、ENTER キーを押します。  

6.  コマンド プロンプトで「**終了**し、enter キーを押して、コマンド プロンプト ウィンドウを閉じます。  

#### <a name="to-build-the-receiver-run-time-project"></a>受信側をビルドするプロジェクトの実行時  

1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**Windows エクスプ ローラー**します。  

2.  移動し、 \<*サンプル パス*\> **"\AdaptersDevelopment\File Adapter\Runtime"** ディレクトリ、およびダブルクリック**DotNetFile.sln**.  

3.  ソリューション エクスプ ローラーで、アダプタのレシーバ ランタイム プロジェクトを再構築するを右クリックして**DotNetFile**、 をクリックし、**リビルド**。  

4.  **ファイル** メニューのをクリックして**終了**Visual Studio を終了します。  

#### <a name="to-build-the-adapter-design-time-project"></a>アダプター デザイン時のプロジェクトをビルドするには  

1.  Windows エクスプ ローラーに移動、 \<*サンプル パス*\> **"\AdaptersDevelopment\File Adapter\Design \adapter Management"** ディレクトリ、およびダブルクリックします**AdapterManagement.sln**します。  

2.  ソリューション エクスプ ローラーで右クリック**AdapterManagement**、 をクリックし、**リビルド**します。  

3.  **ファイル** メニューのをクリックして**終了**Visual Studio を終了します。  

#### <a name="to-register-the-sample-static-adapter"></a>サンプルの静的アダプターを登録するには  

1. Windows エクスプ ローラーに移動、 \<*サンプル パス*\> **"\AdaptersDevelopment\File アダプター"** ディレクトリ。  

2. サンプル アダプターをレジストリに追加するには、ダブルクリック**StaticAdapterManagement.reg**します。  

   > [!NOTE]
   >  StaticAdapterManagement.reg には、C:\Program files \microsoft BizTalk Server にハードコードされたパスが含まれています。\\します。 インストールしなかった場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]%ProgramFiles%\Microsoft BizTalk server で BizTalk Server 2009 または BizTalk Server 2006 R2 から BizTalk Server のインストールをアップグレードする場合、または BizTalk Server を実行しているコンピューターにインストールした場合は、ディレクトリ、Windows の 64 ビット版、ファイル StaticAdapterManagement.reg のパスを適切に変更する必要があります。 既定では、BizTalk Server は、%programfiles(x86) %\Microsoft 64 ビット版 Windows を実行しているコンピューター上の BizTalk server \ ディレクトリにインストールされます。 指定されたファイルの正しい場所を指す"InboundAssemblyPath"、"OutboundAssemblyPath"および"AdapterMgmtAssemblyPath"の値に関連付けられたパスを更新します。  
   > 
   > [!IMPORTANT]
   >  BizTalk を 64 ビット コンピューターにインストールすると、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **StaticAdapterManagement.reg**レジストリ ファイル。  

3. **レジストリ エディター**ダイアログ ボックスで、をクリックして**はい**サンプル アダプターをレジストリに追加し、クリックする **[ok]** 。  

4. Windows エクスプ ローラーを閉じる、**ファイル** メニューのをクリックして**閉じます**します。  

#### <a name="to-install-the-sample-static-adapter"></a>サンプルの静的アダプターをインストールするには  

1. をクリックして**開始**を選択します**すべてのプログラム**を選択します[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、し、 **BizTalk Server 管理**します。  

2. BizTalk Server 管理コンソールで、クリックして展開**BizTalk Server 管理**をクリックして展開**BizTalk グループ**をクリックして展開**プラットフォームの設定**.  

3. 右クリックして**アダプター**、 をクリックして**新規**、 をクリックし、**アダプター**します。  

4. **アダプターの追加** ダイアログ ボックスで、次の操作を行います。  


   |  プロパティ   |                      目的                       |
   |-------------|-------------------------------------------------------|
   |  **名前**   |                   型**静的**します。                    |
   | **アダプター** | 選択**Static dotnetfile**ドロップダウン リストから。 |
   | **解説** |               型**アダプター サンプル**します。                |


5. **[OK]** をクリックします。  

    静的アダプターは、BizTalk 管理コンソールの右側のウィンドウにあるアダプターの一覧に表示されます。  

#### <a name="to-stop-and-restart-the-host-instance"></a>停止して、ホスト インスタンスを再起動するには  

1. をクリックして**開始**を選択します**すべてのプログラム**を選択します[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]を選択し、 **BizTalk Server 管理**します。  

2. BizTalk Server 管理コンソールで、クリックして展開**BizTalk Server 管理**をクリックして展開**BizTalk グループ**をクリックして展開**プラットフォームの設定**をクリックして**ホスト インスタンス**します。 右側のウィンドウで、[biztalkserverapplication] を選択します。  

3. 結果ウィンドウで、ホスト インスタンス (通常は、コンピューター名) を右クリックし、**再起動**します。  

### <a name="running-this-sample"></a>このサンプルの実行  

##### <a name="to-run-the-file-adapter-sample"></a>ファイル アダプター サンプルを実行するには  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**Windows エクスプ ローラー**します。  

2. BizTalk Server のインストール ドライブには、次のフォルダーを作成します。  

   -   *\<drive\>* : **\Temp**  

   -   *\<drive\>* : **\Temp\Send**  

   -   *\<drive\>* : **\Temp\Receive**  

3. Windows エクスプ ローラーを閉じる、**ファイル** メニューのをクリックして**閉じます**します。  

4. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

5. 右クリックし、 **BizTalk Server 管理**ノード**既存グループへの接続**します。  

6. **既存の BizTalk Server 構成データベースへの接続** ダイアログ ボックスで、次の操作を行います。  

   > [!NOTE]
   >  BizTalk 管理データベースは、BizTalk 構成データベースとも呼ばれます。  

   |    プロパティ    |                                                                                    目的                                                                                     |
   |----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **SQL Server** |                                                                              型**します。** (ピリオド)。                                                                               |
   |  **[データベース]**  | 構成ウィザードによって作成された BizTalk 管理データベースの名前を選択します。 構成ウィザードで使用される既定のデータベース名は**BizTalkMgmtDb**します。 |


7. **[OK]** をクリックします。  

8. 展開、 **BizTalk グループ [*サーバー名*]** 内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開、**アプリケーション**ノードを展開、 **BizTalk アプリケーション 1**ノード。  

9. 右クリックし、**送信ポート**ノードをクリック**新規**を選択します**静的な一方向送信ポート**、順にクリックします**OK**します。  

10. **送信ポートのプロパティ**ダイアログ ボックスで、**全般**次の操作を行います。  


    |      プロパティ      |                                                                                                                                                                                   目的                                                                                                                                                                                   |
    |--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |      **名前**      |                                                                                                                                                                             型**AdapterSend**します。                                                                                                                                                                              |
    | **トランスポートの種類** | 選択**静的** をクリックして、ドロップダウン リストから**構成**します。<br /><br /> -、**ディレクトリ**ボックスに「* **\<ドライブ\>*:\Temp\Send**します。<br />-、**ファイル モード**ボックスで、 **CreateNew**します。<br />-、**ファイル名**ボックスに「 **%MessageID%.xml**します。<br />- **OK**します。<br />- **URI**フィールドを表示する必要があります * **\<ドライブ\>*:\Temp\Send\\%MessageID%.xml**します。 |
    | **送信パイプライン**  |                                                                                                                                   選択**PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)** 、 をクリックし、 **OK**。                                                                                                                                    |


11. 下、 **BizTalk アプリケーション 1**  ノードをクリック**受信ポート**、選択および**新規/一方向の受信ポート**します。  

12. **新しい受信ポートを作成** ダイアログ ボックスで、**受信ポートの種類を指定**ボックスで、**一方向の受信ポート**ドロップダウン リストから、ボックスの一覧し、順にクリックします**Ok**します。  

13. **受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **adapterreceive**、順にクリックします**OK**。  

14. 下、 **BizTalk アプリケーション 1**ノードを右クリックして**受信場所**、選択と**新規/一方向の受信場所**します。  

15. **受信ポートの選択**ダイアログ ボックスで選択**adapterreceive**  をクリックし、 **OK**。  

16. **受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。  


    |       プロパティ       |                                                                                                                                                                                               目的                                                                                                                                                                                                |
    |----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |       **名前**       |                                                                                                                                                                                     型**AdapterReceiveLocation**                                                                                                                                                                                     |
    |  **トランスポートの種類**  |                                                                                                                                                  選択**静的**ヒットし、ドロップダウン リストから**構成**にこれらの残りのプロパティにアクセスします。                                                                                                                                                  |
    |       **URI**        | 省略記号ボタンをクリックします ( **.** ).<br />-、**数 Of Files In Batch**ボックスに「 **20**します。<br />-、**ディレクトリ**ボックスに「* **\<ドライブ\>*:\Temp\Receive**します。<br />-、**ファイル マスク**プロパティに設定されて **\*.xml**します。<br />-、**のポーリング間隔**ボックスに「 **5**、 をクリック**OK**します。<br />-、 **URI**ラベルが含まれます * **\<ドライブ\>*:\Temp\Receive\\\*.xml**します。 |
    | **受信ハンドラー**  |                                                                                                                                                                      選択**BizTalkServerApplication**ドロップダウン リストから。                                                                                                                                                                       |
    | **受信パイプライン** |                                                                                                                                                                             選択**XMLReceive**ドロップダウン リストから。                                                                                                                                                                              |


17. **[OK]** をクリックします。  

     進みます*構築、デプロイ、およびサンプル アダプター バインド*します。  

### <a name="building-deploying-and-binding-the-sample-adapter"></a>ビルド、配置、およびサンプル アダプターのバインド  
 アダプターが運用する前に、プロジェクトをビルドしてにポートをオーケストレーションをバインドし、アダプターを参加させる必要があります。  

##### <a name="to-create-a-strong-name-key-for-the-static-adapter"></a>静的アダプターの厳密な名前キーを作成するには  

1.  開始**Visual Studio コマンド プロンプト**します。  

2.  コマンド プロンプトで、現在のディレクトリを変更する、 \<*サンプル パス*\> **\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter ハーネス**ディレクトリ。  

3.  コマンド プロンプトで「 **sn – k AdapterHarness.snk**と入力し、します。  

4.  **[OK]** をクリックします。  

##### <a name="to-build-the-adapter-harness-project"></a>アダプター ハーネス プロジェクトをビルドするには  

-   ソリューション エクスプ ローラーで右クリック**adapterharnessproject**、 をクリックし、**リビルド**します。  

##### <a name="to-deploy-the-adapter-harness-project"></a>アダプター ハーネス プロジェクトを配置するには  

1.  ソリューション エクスプ ローラーでプロジェクトが再構築時に、右クリック**adapterharnessproject**、 をクリックし、**デプロイ**します。  

2.  BizTalk Server 管理コンソールには、展開をクリックしたプロジェクトを選択します。**更新**します。  

##### <a name="to-bind-the-orchestration-with-the-ports"></a>ポートとオーケストレーションをバインドするには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、適切な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション、展開、**オーケストレーション**ノード。  

2. 右クリックして**AdapterHarness.AdapterHarnessType**、 をクリックし、**バインド**します。  

3. **ポートのバインドのプロパティ - adapterharness.adapterharnesstype-Binding Configurations**  ダイアログ ボックスで、次の操作を行います。  


   |          プロパティ          |                     目的                     |
   |----------------------------|----------------------------------------------------|
   | **AdapterFileReceivePort** | 選択 **[adapterreceive]** ドロップダウン リストから。 |
   |  **AdapterFileSendPort**   |  選択**AdapterSend**ドロップダウン リストから。   |


4. 左側のウィンドウで次のようにクリックします。**ホスト**します。  

5. **ホスト**ボックスで、 **BizTalkServerApplication**クリックしてドロップダウン リストから**OK**。  

   続行する*サンプル アダプターを管理する*します。  

### <a name="administering-the-sample-adapter"></a>サンプル アダプターの管理  
 BizTalk 管理コンソールで、サンプル アダプターに対する管理タスクを完了するとします。  

##### <a name="to-administer-the-file-adapter-sample"></a>ファイル アダプターのサンプルを管理するには  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. 左側のウィンドウで、クリックして展開**アプリケーション**をクリックして展開**BizTalk アプリケーション 1**、 をクリック**受信場所**します。  

3. 確認、 **[adapterreceive]** 状態が**有効**します。  

    状態でない場合**有効**を右クリックして **[adapterreceive]** 右側のウィンドウでクリック**を有効にする**します。  

4. 左側のウィンドウで次のようにクリックします。**オーケストレーション**いることを確認および**AdapterHarness.AdapterHarnessType**は**参加済み**します。 右クリックして**AdapterHarness.AdapterHarnessType**、 をクリックし、**参加**(AdapterHarness.AdapterHarnessType が既に参加している場合、**参加**メニュー オプションは、使用不可)。  

5. 右クリック**AdapterHarness.AdapterHarnessType**選択**開始**します。 このオーケストレーションの状態に変更する必要があります**を実行している**します。  

   続行する*サンプル アダプターのテスト*します。  

### <a name="testing-the-sample-adapter"></a>サンプル アダプターのテスト  
 サンプル アダプターを展開した後は、停止して、ホスト インスタンスを再起動する必要があります。 運用環境に配置する前に、サンプル アダプターをテストすることが重要です。  

##### <a name="to-stop-and-restart-the-host-instance"></a>停止して、ホスト インスタンスを再起動するには  

1.  **BizTalk Server 管理**コンソールをクリックして展開**BizTalk Server 管理**をクリックして展開**BizTalk グループ**をクリックして展開**プラットフォームの設定**クリック**ホスト インスタンス**します。 右側のウィンドウで、[biztalkserverapplication] を選択します。  

2.  ホスト インスタンス (通常は、コンピューター名) を右クリックし、をクリックし、**停止**します。  

     ホスト インスタンスの状態に変わる**Stopped**します。  

3.  ホスト インスタンスを右クリックし、クリックして**開始**します。  

     ホスト インスタンスの状態に変わる**を実行している**します。  

##### <a name="to-test-the-sample-static-adapter-runtime"></a>サンプルの静的アダプターのランタイムをテストするには  

1.  Windows エクスプ ローラーに移動、 \<*サンプル パス*\> **\AdaptersDevelopment\File アダプター**ディレクトリ、および InstanceXML.xml ファイルをクリップボードにコピーします。  

2.  移動します *\<ドライブ\>* : **\Temp\Receive** Instance.xml ファイルをフォルダーに貼り付けます。  

     場合、送信と受信アダプターが作業しているから、ファイルを移動する必要があります、 *\<ドライブ\>* : **\Temp\Receive**フォルダーを *\<ドライブ\>* : **\Temp\Send**フォルダー。  

##### <a name="to-test-the-sample-add-adapter-wizard-functionality-for-the-sample-static-adapter"></a>サンプルの静的アダプターのサンプル アダプターの追加ウィザードの機能をテストするには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック **[adapterharnessproject]** 、をポイント**追加**、クリックして**生成した項目の追加**です。  

2. **生成項目の追加 - [adapterharnessproject]** ダイアログ ボックスで、をクリックして**アダプター メタデータの追加**、順にクリックします**オープン**します。  

    登録済みアダプターの一覧が表示されます。  

3. 選択**Static dotnetfile**、 をクリックし、**次**。  

    アダプターによって公開されるサービスの構成が表示されます。  

4. 展開**サービス組織**、**医療**、 をクリックし、**管理**します。  

    注意**適格性**他のノードからを異なる方法で表示します。 **適格性**サービス ノードを選択できます。 他のノードは、特定のサービスを記述しない組織ノードです。  

5. 選択、**適格性**ノード、およびクリック**完了**。  

    BizTalk では、.odx ファイルと .xsd ファイルをプロジェクトにインポートします。  

    スキーマ、PortTypes、操作、および BizTalk プロジェクトのスケジュールにアダプターからインポートされた Messagetype を使用できます。  

## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 インターフェイス:IBaseMessage、IPropertyBag、IBTTransportProxy  

 クラス (ベース アダプターから):AsyncTransmitterEndpoint、AsyncTransmitter、BatchMessage、ControlledTermination、ReceiverEndpoint、DotNetFileCommonProperties、BatchOperationType  

### <a name="comments"></a>コメント  
 サンプル アダプターを完了するを参照してください詳細については、カスタムの静的または動的アダプターを作成するサンプル アダプターを変更できます[アダプターのデザイン時構成](../core/adapter-design-time-configuration.md)します。  

## <a name="see-also"></a>参照  
 [アダプタ サンプル – 使用状況](../core/adapter-samples-usage.md)   
 [アダプターの登録](../core/registering-an-adapter.md)