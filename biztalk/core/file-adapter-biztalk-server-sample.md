---
title: "ファイル アダプター (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, File adapters
- File adapters, examples
ms.assetid: d59cecb4-6353-44d5-b8d6-316446758536
caps.latest.revision: "46"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de68c57c6b435f85edf630a7b224c5d58ffd0cd6
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="file-adapter-biztalk-server-sample"></a>ファイル アダプター (BizTalk Server サンプル)
ファイル アダプター サンプルは、Microsoft Visual c# .NET で Microsoft BizTalk Server を使用する書き込まれます。 このサンプルでは動的アダプターまたは静的アダプターのいずれかをビルドするコードが提供されますが、  以下では静的アダプターの概要手順のみを説明します。 静的アダプターとは、静的な一連のスキーマが付属した、カスタム ユーザー インターフェイスのないアダプターのことです。 動的アダプターにはカスタム ユーザー インターフェイスが備わっており、動的な一連のスキーマが付属していることもあります。 静的アダプターと動的アダプターでは両方とも、アダプターの追加ウィザードを使用してスキーマを BizTalk プロジェクトに追加できます。  
  
> [!NOTE]
>  ファイル アダプター サンプルは、BizTalk Server に付属しているネイティブ ファイル アダプターと同じではありません。 したがって、このサンプルで使用するトランスポートの種類を選択する際は、[FILE] ではなく [静的] を選択してください。  
  
 カスタム ユーザー インターフェイスと動的な一連のスキーマを備えた動的アダプターを使用する場合、アダプター管理側ではコードを追加する必要があります。 動的な一連のスキーマの使用をより深く理解するを参照してください[動的デザイン時アダプター構成](../core/dynamic-design-time-adapter-configuration.md)です。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 サンプル アダプターがファイル フォルダーからファイルをコピー、メッセージとして BizTalk に送信またはからのメッセージを受け取る[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ファイル フォルダーにドロップするとします。 このサンプルでは動的アダプターまたは静的アダプターのいずれかをビルドするコードが提供されますが、以下では静的アダプターの概要手順のみを説明します。 静的アダプターとは、静的な一連のスキーマが付属した、カスタム ユーザー インターフェイスのないアダプターのことです。 動的アダプターにはカスタム ユーザー インターフェイスが備わっており、動的な一連のスキーマが付属していることもあります。 静的アダプターと動的アダプターでは両方とも、アダプターの追加ウィザードを使用してスキーマを BizTalk プロジェクトに追加できます。  
  
 このサンプル ファイル アダプターは、他のカスタム アダプターを作成する際にテンプレートとして使用できます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>**\AdaptersDevelopment\File アダプター**  
  
> [!NOTE]
>  既定の場所\<*サンプル パス*\>は*%programfiles%*\Microsoft BizTalk Server\SDK\Samples 32 ビットを実行するコンピューターに BizTalk Server がインストールされている場合Windows のバージョンです。 既定の場所\<*サンプル パス*\>は*%programfiles (x86) %*\Microsoft BizTalk Server\SDK\Samples 64 を実行するコンピューターに BizTalk Server がインストールされている場合ビット版 Windows です。 関連付けられている値を決定する、 *%programfiles%* または *%programfiles (x86) %* 環境変数の型 **echo %programfiles%** または **echo %programfiles (x86) %** コマンド プロンプトと ENTER キーを押します。 64 ビット オペレーティング システムでこのサンプルを実行している場合から .reg ファイルのいずれかのすべての参照を変更する必要があります。 **%programfiles%** に **%programfiles (x86) %** .reg ファイルを実行する前にします。  
  
 このサンプルに含まれるファイルとその目的を次の表に示します。  
  
|\File Adapter のファイル|Description|  
|--------------------------|-----------------|  
|\BizTalk Project のファイル|サンプル アダプターのテストに使用するアダプター ハーネス プロジェクトが含まれています。|  
|\Design Time のファイル|デザイン時および管理のプロジェクト (AdapterManagement.csproj) が含まれています。|  
|\Runtime のファイル|ランタイム ファイル コピーの受信および送信プロジェクト (DotNetFile.csproj) が含まれています。|  
|DynamicAdapterManagement.reg|サンプルの動的アダプターを登録します。|  
|Instance.xml|ファイル アダプターを通過するサンプル ファイルです。|  
|StaticAdapterManagement.reg|サンプルの静的アダプターを登録します。|  
  
|\BizTalk Project\Adapter Harness のファイル|Description|  
|----------------------------------------------|-----------------|  
|AdapterHarness.odx、AdapterHarness.sln、AdapterHarnessProject.btproj|BizTalk プロジェクトのプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルを提供します。|  
|mySchema.xsd|アダプターの受信部分からのハーネス オーケストレーションに必要とされる Instance.xml スキーマのほか、オーケストレーションによりアダプターの送信部分に渡される Instance.xml のスキーマを提供します。|  
  
|\Design Time\Adapter Management のファイル|Description|  
|---------------------------------------------|-----------------|  
|AdapterManagement.cs、AdapterManagement.csproj、AdapterManagement.sln|アダプター デザイン時用のプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。|  
|AssemblyInfo.cs|このサンプルのアセンブリ情報が含まれています。|  
|CategorySchema2.xml|サンプル アダプターでは使用されません。|  
|CategorySchema.xml|静的アダプターのサービス構成ツリーが含まれています。|  
|DotNetFileResource.resx|リソースが含まれています。|  
|ReceiveHandler.xsd、ReceiveLocation.xsd|受信側のハンドラーおよびエンドポイントのカスタム プロパティ スキーマが含まれています。|  
|service1.wsdl|アダプターの操作定義が含まれています。|  
|TransmitHandler.xsd、TransmitLocation.xsd|送信側のハンドラーおよびエンドポイントのカスタム プロパティ スキーマが含まれています。|  
  
|\Runtime のファイル|Description|  
|---------------------|-----------------|  
|DotNetFile.csproj、DotNetFile.sln、<br /><br /> AssemblyInfo.cs、<br /><br /> DotNetFileExceptions.cs、DotNetFileProperties.cs、DotNetFileReceiver.cs、DotNetFileReceiverEndPoint.cs、DotNetFileTransmitter.cs、<br /><br /> DotNetFileTransmitterEndpoint.cs、<br /><br /> DotNetFileAsyncTransmitterBatch.cs、<br /><br /> BatchMessage.cs|ランタイム ファイル コピーの送信および受信アダプター用のファイルです。 これらのファイルをカスタム コンポーネント用に修正し、新しい名前で保存できます。<br /><br /> DotNetFile.csproj と DotNetFile.sln はプロジェクト ファイルとソリューション ファイルです。<br /><br /> AssemblyInfo.cs には、このサンプルのアセンブリ情報が含まれています。<br /><br /> DotNetFileReceiver.cs は受信場所からファイルを読み取り、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信します。<br /><br /> DotNetFileExceptions.cs はメッセージ処理で発生する例外を処理するコードを実装します。<br /><br /> DotNetFileProperties.cs には、送信操作と受信操作の両方に必要な共通プロパティが含まれています。<br /><br /> BatchMessage.cs は、バッチによるメッセージ処理を実装します。<br /><br /> DotNetFileReceiverEndPoint.cs は、受信場所/URI に対応するクラスで、  新しいメッセージ用の特定のフォルダーのポーリングを処理します。<br /><br /> DotNetFileTransmitter.cs は、DotNetFile 送信アダプターの単一クラスです。 この種類のアダプターの送信ポートに送られるすべてのメッセージは、このクラスで処理されます。<br /><br /> DotNetFileTransmitterEndpoint.cs はメッセージの送信を処理します。|  
  
|\SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2 のファイル|Description|  
|--------------------------------------------------------------------|-----------------|  
|Adapter.cs、AdapterException.cs、AsyncTransmitter.cs、batch.cs、ConfigProperties.cs、ControlledTermination.cs、IManageEndpoints.cs、Receiver.cs、ReceiverEndpoint.cs|ベース アダプターを構成するクラスを提供します。 これらのクラスを使用して、独自のアダプターを作成できます。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 サンプル ファイル アダプターは、他のカスタム アダプターを作成する際にテンプレートとして使用します。  
  
## <a name="building-this-sample"></a>このサンプルのビルド  
  
> [!IMPORTANT]
>  BizTalk 環境が 64 ビットである、またはインストール場所が変更されている場合は、それに合わせて OutboundAssemblyPath、InboundAssemblyPath、および AdapterMgmtAssemblyPath を変更する必要があります。  
  
 次の手順を使用して、ファイル アダプターのサンプルをビルドおよび初期化します。  
  
#### <a name="to-create-a-strong-name-key-for-the-dotnetfileadapter-projects-and-the-base-adapter-project"></a>DotNetFileAdapter プロジェクトおよびベース アダプター プロジェクト用の厳密な名前のキーを作成するには  
  
1.  開始 **Visual Studio コマンド プロンプト**します。  
  
    > [!NOTE]
    >  管理者としてコマンド プロンプトを実行します。  
  
2.  現在のディレクトリを変更、 \<*サンプル パス*\>**\AdaptersDevelopment\BaseAdapter\v1.0.2**ディレクトリ。  
  
3.  コマンド プロンプトで「 **sn – k BaseAdapter.snk** ENTER キーを押します。 以前に実行されているその他のサンプルの結果としてこの .snk ファイルが既にあります。 この場合は、手順 4. に進んでください。  
  
4.  現在のディレクトリを変更、 \<*サンプル パス*\>\\**AdaptersDevelopment\File Adapter\Runtime**ディレクトリ。  
  
5.  コマンド プロンプトで「 **sn – k DotNetFileAdapter.snk** ENTER キーを押します。  
  
6.  コマンド プロンプトで「 **終了** し、enter キーを押してコマンド プロンプト ウィンドウを閉じます。  
  
#### <a name="to-build-the-receiver-run-time-project"></a>レシーバー ランタイム プロジェクトをビルドするには  
  
1.  をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **アクセサリ**, 、 をクリックし、 **Windows エクスプ ローラー**します。  
  
2.  移動し、 \<*サンプル パス*\>**"\AdaptersDevelopment\File Adapter\Runtime"**ディレクトリ、およびダブルクリック**DotNetFile.sln**.  
  
3.  アダプタのレシーバ ランタイム プロジェクトのソリューション エクスプ ローラーでを再構築を右クリックし **DotNetFile**, 、クリックして **を再構築**します。  
  
4.  **ファイル**  メニューのをクリックして **終了** Visual Studio を終了します。  
  
#### <a name="to-build-the-adapter-design-time-project"></a>アダプター デザイン時のプロジェクトをビルドするには  
  
1.  Windows エクスプ ローラーに移動、 \<*サンプル パス*\>**"\AdaptersDevelopment\File Adapter\Design time \adapter Management"**ディレクトリ、およびをダブルクリック**AdapterManagement.sln**です。  
  
2.  ソリューション エクスプ ローラーで右クリック **AdapterManagement**, 、クリックして **を再構築**します。  
  
3.  **ファイル**  メニューのをクリックして **終了** Visual Studio を終了します。  
  
#### <a name="to-register-the-sample-static-adapter"></a>サンプルの静的アダプターを登録するには  
  
1.  Windows エクスプ ローラーに移動、 \<*サンプル パス*\>**"\AdaptersDevelopment\File アダプター"**ディレクトリ。  
  
2.  サンプル アダプターをレジストリに追加するにはダブルクリック **StaticAdapterManagement.reg**します。  
  
    > [!NOTE]
    >  StaticAdapterManagement.reg には、C:\Program files \microsoft BizTalk Server へのハードコードされたパスが含まれています。\\です。 インストールしていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]%ProgramFiles%\Microsoft BizTalk server で BizTalk Server 2009 または BizTalk Server 2006 R2 から BizTalk Server のインストールをアップグレードする場合、または BizTalk Server を実行しているコンピューターにインストールした場合は、ディレクトリ、64 ビット バージョンの Windows で、ファイル StaticAdapterManagement.reg のパスを適切に変更する必要があります。 既定では、BizTalk Server は、%programfiles(x86) %\Microsoft 64 ビット バージョンの Windows を実行しているコンピューター上の BizTalk server \ ディレクトリにインストールされます。 "InboundAssemblyPath"、"OutboundAssemblyPath"、および "AdapterMgmtAssemblyPath" の値に関連付けられたパスを更新し、指定されたファイルの正しい場所を指すようにします。  
  
    > [!IMPORTANT]
    >  BizTalk を 64 ビット コンピューターにインストールすると、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **StaticAdapterManagement.reg** レジストリ ファイルです。  
  
3.  **レジストリ エディター** ダイアログ ボックスで、をクリックして **[はい]** サンプル アダプターをレジストリに追加する **[ok]**します。  
  
4.  Windows エクスプ ローラーを閉じる、 **ファイル**  メニューのをクリックして **閉じる**します。  
  
#### <a name="to-install-the-sample-static-adapter"></a>サンプルの静的アダプターをインストールするには  
  
1.  をクリックして**開始****すべてのプログラム**を選択[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、し、 **BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソール内をクリックして展開 **BizTalk Server 管理コンソール**, をクリックして展開 **BizTalk グループ**, をクリックして展開 **プラットフォームの設定**します。  
  
3.  右クリックして **アダプター**, をクリックして **新規**, 、順にクリック **アダプター**します。  
  
4.  **アダプターの追加**  ダイアログ ボックスで、次の操作です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名**|型 **静的**します。|  
    |**アダプター**|選択 **Static DotNetFile** ドロップ ダウン リストからです。|  
    |**コメント**|型 **アダプターのサンプル**します。|  
  
5.  **[OK]**をクリックします。  
  
     これで、BizTalk 管理コンソールの右ウィンドウにあるアダプターの一覧に静的アダプターが表示されます。  
  
#### <a name="to-stop-and-restart-the-host-instance"></a>停止して、ホスト インスタンスを再起動するには  
  
1.  をクリックして**開始****すべてのプログラム**を選択[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]を選択し、 **BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソール内をクリックして展開 **BizTalk Server 管理コンソール**, をクリックして展開 **BizTalk グループ**, をクリックして展開 **プラットフォームの設定**  をクリック **ホスト インスタンス**します。 右ペインで、[BizTalkServerApplication] を選択します。  
  
3.  結果ウィンドウで、ホスト インスタンス (通常は、コンピューター名) を右クリックし、クリックして **再起動**します。  
  
### <a name="running-this-sample"></a>このサンプルの実行  
  
##### <a name="to-run-the-file-adapter-sample"></a>ファイル アダプターのサンプルを実行するには  
  
1.  をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **アクセサリ**, 、 をクリックし、 **Windows エクスプ ローラー**します。  
  
2.  BizTalk Server のインストール ドライブに、次のフォルダーを作成します。  
  
    -   *\<drive\>*:**\Temp**  
  
    -   *\<drive\>*:**\Temp\Send**  
  
    -   *\<drive\>*:**\Temp\Receive**  
  
3.  Windows エクスプ ローラーを閉じる、 **ファイル**  メニューのをクリックして **閉じる**します。  
  
4.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
5.  右クリックし、 **BizTalk Server 管理コンソール**  ノード **既存のグループへの接続**します。  
  
6.  **既存の BizTalk Server 構成データベースへの接続**  ダイアログ ボックスで、次の操作です。  
  
    > [!NOTE]
    >  BizTalk 管理データベースは、BizTalk 構成データベースとも呼ばれます。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**SQL Server**|型 **します。** 」 (ピリオド) を入力します。|  
    |**データベース**|構成ウィザードで作成された BizTalk 管理データベースの名前を選択します。 構成ウィザードで使用される既定のデータベース名は **BizTalkMgmtDb**します。|  
  
7.  **[OK]**をクリックします。  
  
8.  展開、 **BizTalk グループ [*サーバー名*]**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開、**アプリケーション** ノードを展開、 **BizTalk アプリケーション 1**ノード。  
  
9. 右クリックし、 **送信ポート**  ノードをクリック **新規**,  **静的な一方向送信ポート**, 、 をクリックし、 **ok**します。  
  
10. **送信ポートのプロパティ** ダイアログ ボックスで、 **全般**, 、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名**|型 **AdapterSend**します。|  
    |**トランスポートの種類**|選択 **静的**  をクリック、ドロップ ダウン リストから **構成**します。<br /><br /> -、**ディレクトリ**ボックスに、入力 ***\<ドライブ\>*:\Temp\Send**です。<br />-、 **ファイル モード** ボックスで、 **CreateNew**します。<br />-、 **ファイル名** ボックスに、入力 **%MessageID%.xml**します。<br />- **OK**します。<br />- **URI**フィールドを表示する必要があります ***\<ドライブ\>*:\Temp\Send\\%MessageID%.xml**です。|  
    |**送信パイプライン**|選択 **PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)**, 、 をクリックし、 **OK**します。|  
  
11. 下にある、 **BizTalk アプリケーション 1**  ノードをクリック **受信ポート**, を選択して **新規/一方向の受信ポート**します。  
  
12. **新しい受信ポートを作成する** ダイアログ ボックスで、 **受信ポートの種類を指定** ボックスで、 **一方向の受信ポート** クリックしてドロップダウン リストから **[ok]**します。  
  
13. **受信ポートのプロパティ** ダイアログ ボックスで、 **名前** ボックスに、入力 **AdapterReceive**, 、 をクリックし、 **ok**します。  
  
14. 下にある、 **BizTalk アプリケーション 1** ノードを右クリックして **受信場所**, を選択して **新規/一方向の受信場所**します。  
  
15. **受信ポートの選択**  ダイアログ ボックスで選択 **AdapterReceive**  をクリックし、 **OK**します。  
  
16. **受信場所のプロパティ**  ダイアログ ボックスで、次の操作です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名**|型 **AdapterReceiveLocation**|  
    |**トランスポートの種類**|選択 **静的** ヒット、ドロップ ダウン リストから **構成** にこれらの残りのプロパティにアクセスします。|  
    |**URI**|省略記号ボタンをクリックする (**...**)。<br />-、 **数 Of Files In Batch** ボックスに、入力 **20**します。<br />-、**ディレクトリ**ボックスに、入力 ***\<ドライブ\>*:\Temp\Receive**です。<br />-、 **ファイル マスク** にプロパティが設定されている **\*.xml**します。<br />-、 **のポーリング間隔** ボックスに、入力 **5**, 、 をクリック **OK**します。<br />-、 **URI**ラベルが含まれています ***\<ドライブ\>*:\Temp\Receive\\\*.xml**です。|  
    |**受信ハンドラー**|選択 **BizTalkServerApplication** ドロップ ダウン リストからです。|  
    |**受信パイプライン**|選択 **XMLReceive** ドロップ ダウン リストからです。|  
  
17. **[OK]**をクリックします。  
  
     」に進みます *ビルド、配置、およびサンプル アダプター バインド*します。  
  
### <a name="building-deploying-and-binding-the-sample-adapter"></a>サンプル アダプターのビルド、展開、およびバインド  
 アダプターを実際に使用するには、その前にプロジェクトをビルドし、オーケストレーションにポートをバインドして、アダプターを参加させる必要があります。  
  
##### <a name="to-create-a-strong-name-key-for-the-static-adapter"></a>静的アダプター用の厳密な名前のキーを作成するには  
  
1.  開始 **Visual Studio コマンド プロンプト**します。  
  
2.  コマンド プロンプトでは、現在のディレクトリを変更する、 \<*サンプル パス*\>**\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter ハーネス**ディレクトリ。  
  
3.  コマンド プロンプトで「 **sn – k AdapterHarness.snk**, 、とし、enter キーを押します。  
  
4.  **[OK]**をクリックします。  
  
##### <a name="to-build-the-adapter-harness-project"></a>アダプター ハーネス プロジェクトをビルドするには  
  
-   ソリューション エクスプ ローラーで右クリック **[adapterharnessproject]**, 、クリックして **を再構築**します。  
  
##### <a name="to-deploy-the-adapter-harness-project"></a>アダプター ハーネス プロジェクトを展開するには  
  
1.  ソリューション エクスプ ローラーでプロジェクトがリビルドされるときに、右クリック **[adapterharnessproject]**, 、クリックして **展開**します。  
  
2.  BizTalk Server 管理コンソールで、プロジェクトを選択および展開しました をクリックし、 **更新**します。  
  
##### <a name="to-bind-the-orchestration-with-the-ports"></a>オーケストレーションにポートをバインドするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、適切な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション、展開、**オーケストレーション**ノード。  
  
2.  右クリック **AdapterHarness.AdapterHarnessType**, 、クリックして **バインド**します。  
  
3.  **ポート バインドのプロパティ - adapterharness.adapterharnesstype-Binding Configurations**  ダイアログ ボックスで、次の操作です。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**AdapterFileReceivePort**|選択 **AdapterReceive** ドロップ ダウン リストからです。|  
    |**AdapterFileSendPort**|選択 **AdapterSend** ドロップ ダウン リストからです。|  
  
4.  左のウィンドウで **ホスト**します。  
  
5.  **ホスト** ボックスで、 **BizTalkServerApplication** クリックしてドロップダウン リストから **OK**します。  
  
 」に進みます *サンプル アダプターを管理する*です。  
  
### <a name="administering-the-sample-adapter"></a>サンプル アダプターの管理  
 BizTalk 管理コンソールで、サンプル アダプターに対する管理タスクを実行します。  
  
##### <a name="to-administer-the-file-adapter-sample"></a>ファイル アダプターのサンプルを管理するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  左側のウィンドウで、クリックして展開 **アプリケーション**, をクリックして展開 **BizTalk アプリケーション 1**, 、 をクリック **受信場所**します。  
  
3.  確認、 **AdapterReceive** 状態が  **Enabled**します。  
  
     状態がない場合 **有効**, を右クリックして **AdapterReceive** をクリックして右側のペイン **を有効にする**です。  
  
4.  左のウィンドウで **オーケストレーション** いることを確認および **AdapterHarness.AdapterHarnessType** は **参加している**します。 右クリックして **AdapterHarness.AdapterHarnessType**, 、 をクリックし、 **Enlist** (AdapterHarness.AdapterHarnessType が既に参加している場合、 **Enlist** メニュー オプションは使用できません)。  
  
5.  右クリック **AdapterHarness.AdapterHarnessType** 選択 **開始**します。 このオーケストレーションの状態に変わります **を実行している**します。  
  
 」に進みます *サンプル アダプターのテスト*します。  
  
### <a name="testing-the-sample-adapter"></a>サンプル アダプターのテスト  
 サンプル アダプターを展開したら、ホスト インスタンスを停止して再起動する必要があります。 サンプル アダプターを運用する前には必ずテストしてください。  
  
##### <a name="to-stop-and-restart-the-host-instance"></a>停止して、ホスト インスタンスを再起動するには  
  
1.  **BizTalk Server 管理コンソール** コンソールをクリックして展開 **BizTalk Server 管理コンソール**, をクリックして展開 **BizTalk グループ**, をクリックして展開 **プラットフォームの設定**  をクリック **ホスト インスタンス**します。 右ペインで、[BizTalkServerApplication] を選択します。  
  
2.  ホスト インスタンス (通常は、コンピューター名) を右クリックし、 **停止**します。  
  
     ホスト インスタンスの状態に変わる **Stopped**します。  
  
3.  ホスト インスタンスを右クリックし、 **開始**します。  
  
     ホスト インスタンスの状態に変わる **を実行している**します。  
  
##### <a name="to-test-the-sample-static-adapter-runtime"></a>サンプルの静的アダプターをランタイムでテストするには  
  
1.  Windows エクスプ ローラーに移動、 \<*サンプル パス*\>**\AdaptersDevelopment\File アダプター**ディレクトリ、および InstanceXML.xml ファイルをクリップボードにコピーします。  
  
2.  移動*\<ドライブ\>*:**\Temp\Receive**し、Instance.xml ファイルをフォルダーに貼り付けます。  
  
     場合、送信と受信を使用しているアダプターからファイルを移動する必要があります、 *\<ドライブ\>*:**\Temp\Receive**フォルダーを*\<ドライブ\>* :**\Temp\Send**フォルダーです。  
  
##### <a name="to-test-the-sample-add-adapter-wizard-functionality-for-the-sample-static-adapter"></a>サンプルの静的アダプターで、サンプルのアダプターの追加ウィザード機能をテストするには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック**[adapterharnessproject]**、をポイント**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成項目の追加 - [adapterharnessproject]** ダイアログ ボックスで、をクリックして **アダプター メタデータの追加**, 、順にクリック **開く**します。  
  
     登録されたアダプターの一覧が表示されます。  
  
3.  選択 **Static DotNetFile**, 、 をクリックし、 **次**します。  
  
     アダプターで公開されるサービス構成が表示されます。  
  
4.  展開 **サービスに関する組織**, 、**医療**, 、クリックして **管理**します。  
  
     注意して **適格性** は他のノードが異なる方法で表示されます。 **対象となる** サービス ノードを選択できます。 他のノードは構成ノードで、特定のサービスを表すものではありません。  
  
5.  選択、 **適格性** ノードをクリックして **完了**します。  
  
     BizTalk では .odx ファイルと .xsd ファイルがプロジェクトにインポートされます。  
  
     これで、アダプターからインポートしたスキーマ、ポートの種類、操作、およびメッセージの種類を BizTalk プロジェクトのスケジュールで使用できます。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用します。  
 インターフェイス: IBaseMessage、IPropertyBag、IBTTransportProxy  
  
 クラス (ベース アダプターから): AsyncTransmitterEndpoint、AsyncTransmitter、BatchMessage、ControlledTermination、ReceiverEndpoint、DotNetFileCommonProperties、BatchOperationType  
  
### <a name="comments"></a>コメント  
 サンプル アダプターを完了すると、詳細については、カスタムの静的または動的アダプターを作成するを参照してくださいサンプル アダプターを変更できます[アダプター デザイン時構成](../core/adapter-design-time-configuration.md)です。  
  
## <a name="see-also"></a>参照  
 [アダプタ サンプル – 使用状況](../core/adapter-samples-usage.md)   
 [アダプターの登録](../core/registering-an-adapter.md)