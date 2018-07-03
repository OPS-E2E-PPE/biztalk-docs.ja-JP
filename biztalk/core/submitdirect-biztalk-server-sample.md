---
title: SubmitDirect (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- receive adapters, examples
- examples, receive adapters
ms.assetid: 3540368b-cf46-4c83-a87b-94aec9cd1b36
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb385fef1f71d247e09ca2ee5a67d2c19fb29d86
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994427"
---
# <a name="submitdirect-biztalk-server-sample"></a>SubmitDirect (BizTalk Server サンプル)
SubmitDirect サンプルは、.NET ベースのアプリケーションから Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に一方向のメッセージおよび要求 - 応答メッセージをプログラムで送信する方法を示します。 このサンプルでは、アダプターに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] API を使用する例を示します。 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを送信するために使用できる、Submit という名前の受信アダプターを提供します。  

## <a name="prerequisites"></a>前提条件  
 このサンプルを実行する前に、BizTalk 分離ホスト ユーザー グループに属するユーザーとしてログオンしていることを確認してください。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、BizTalk アダプタに関連するさまざまな作業を実行する方法を示します。 具体的には、表示する方法。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの外部で実行される分離アダプターを操作します。 Submit アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの外部のプロセスによって作成されるので、分離アダプターです (Submit アダプターは .NET アプリケーションとして起動されます)。  

- メッセージのバッチを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信します。 Submit アダプタは、バッチ メッセージ送信機能を使用して複数のメッセージを同時に送信します。  

- 要求 - 応答パラダイムを使用したメッセージの同期送信と、一方向パラダイムを使用したメッセージの非同期送信を行います。  

- アダプターを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に登録します。 このサンプルでは、アダプタの登録方法を示し、アダプタの登録を自動化する登録実行可能ファイルを提供します。  

  このサンプルは、次の 2 つのサンプルを 1 つにまとめたものです。  

- **一方向のメッセージのバッチを送信します。** コンソール アプリケーション SubmitMessages.exe は、コマンドラインから文字列を受け取るし、それぞれを別々 のメッセージとして送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 送信された各メッセージは、受信場所で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって取得され、パススルー受信パイプラインおよびパススルー送信パイプライン経由で送信された後、テキスト ファイルに書き込まれます。  

- **要求/応答メッセージの送信。** コンソール アプリケーション SubmitRequest.exe はコマンドラインで指定された .xml ファイルを受け取るし、それに送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 この .xml ファイルのスキーマは、2 つの整数フィールドを含む要素を定義します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は .xml ファイルを取得し、それを 1 つの要求 - 応答ポートを使用するオーケストレーションによって処理します。 このとき、マップを使用して、要求に含まれる 2 つの整数の積を表す整数を返す XML 応答メッセージを生成します。 コンソール アプリケーションが応答を受け取ると、結果が表示されます。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\AdaptersDevelopment\SubmitDirect\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                                                                                                                     ファイル                                                                                                                      |                                                                                              説明                                                                                               |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                   Cleanup.bat                                                                                                                    |    必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。    |
|                                                                                                                    Setup.bat                                                                                                                     |                                                                                  このサンプルを作成および初期化します。                                                                                   |
|                                                                                                                 SubmitDirect.sln                                                                                                                 |                                ProcessRequest フォルダの BizTalk プロジェクトとその他のフォルダの Microsoft Visual C# プロジェクトを含むソリューション ファイルです。                                 |
|                                                                                               SubmitMessagesBinding.xml、SubmitRequestBinding.xml                                                                                                |                                                                             ポートのバインドなど、自動化されたセットアップに使用されます。                                                                             |
|                                                              \ProcessRequest フォルダには、次のファイルが含まれます。<br /><br /> DocIn.xsd、DocOut.xsd、Multiplier.odx、Multiply.btm、ProcessRequest.btproj                                                               |                                               要求 - 応答シナリオで整数の乗算を実行する BizTalk プロジェクトを提供します。                                                |
|                                                                       \SubmitMessages フォルダには、次のファイルが含まれます。<br /><br /> AssemblyInfo.cs、SubmitMessages.cs、SubmitMessages.csproj                                                                       |                                コマンド ライン文字列パラメータを別々のメッセージのバッチとして渡すコンソール アプリケーションの Visual C# プロジェクトを提供します。                                |
|                                                                \SubmitRequest フォルダには、次のファイルが含まれます。<br /><br /> AssemblyInfo.cs、DocInstance.xml、SubmitRequest.cs、SubmitRequest.csproj                                                                |                                 乗算する 2 つの整数を含む .xml ファイル (DocInstance.xml) を渡すコンソール アプリケーションの C# プロジェクトを提供します。                                 |
| \TransportProxyUtils フォルダには、次のファイルが含まれます。<br /><br /> AssemblyInfo.cs、MessageHelper.cs、MessagingAPIInterface.cs、MessagingAPIs.cs、ResponseCallBack.cs、TpBatchAsyncCallback.cs、TpBatchAsyncResult.cs、TpBatchStatus.cs、TransportProxyUtils.csproj | Submit アダプタの、同期および非同期のメッセージ送信を行うメソッドとバッチおよび単一の要求メッセージ送信を行うメソッドを実装するランタイム部分の C# プロジェクトを提供します。 |
|                                                              \TransportProxyUtilsReg フォルダには、次のファイルが含まれます。<br /><br /> AssemblyInfo.cs、RegisterAdapter.cs、TransportProxyUtilsReg.csproj                                                               |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にアダプターを登録するために使用するコードを示す Visual C# プロジェクトを提供します。           |
|                                                           \TransportProxyUtilsUI フォルダには、次のファイルが含まれます。<br /><br /> AssemblyInfo.cs、TransportProxyUtilsMgmt.cs、TransportProxyUtilsUI.csproj                                                            |                                                           Submit アダプターのユーザー インターフェイス部分の Visual C# プロジェクトを提供します。                                                           |

## <a name="building-and-initializing-the-sample"></a>サンプルのビルドおよび初期化  

#### <a name="to-build-and-initialize-the-submitdirect-sample"></a>SubmitDirect サンプルをビルドおよび初期化するには  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    \<*パスのサンプル*\>\AdaptersDevelopment\SubmitDirect  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - このサンプルのバッチ送信部分用に、次の出力フォルダを作成します。  

      \<*パスのサンプル*\>\AdaptersDevelopment\SubmitDirect\Out  

   - このサンプル用に、さまざまな [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルします。  

   - Submit アダプターを登録します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成してバインドします。  

     > [!NOTE]
     >  このサンプルは、ポートを作成してバインドする際に、以下の警告を表示します。  
     >   
     >  `Warning: Receive handler not specified for receive location "SubmitDirectRL"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.ProcessRequest.Multiplier"; updating with first available host.`  
     >   
     >  これらの警告は、無視してもかまいません  (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  

   - 受信場所を有効にし、送信ポートとオーケストレーションを開始します。  

     > [!NOTE]
     >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
     > 
     > [!NOTE]
     >  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
     > 
     > [!NOTE]
     >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

## <a name="running-the-sample"></a>サンプルを実行します。  
 このサンプルではファイル アダプタを使用するため、BizTalk ホスト (BizTalkServerApplication) が実行されている必要があります。 次の手順を使用して、SubmitDirect サンプルを実行します。  

#### <a name="to-run-the-batch-submission-portion-of-the-submitdirect-sample"></a>SubmitDirect サンプルのバッチ送信部分を実行するには  

1.  コマンド ウィンドウで、次のフォルダーに移動します。  

     \<*パスのサンプル*\>\AdaptersDevelopment\SubmitDirect\SubmitMessages\bin\Debug  

2.  ファイル SubmitMessages.exe を実行し、コマンド ラインで複数の文字列を渡します。  

     例: SubmitMessages msg1 msg2 msg3  

3.  複数のテキスト ファイルが Out 出力フォルダに作成されることを確認します。これらのファイルには、ファイルごとに 1 つずつ、コマンド ラインで渡された文字列が含まれています。  

#### <a name="to-run-the-requestresponse-portion-of-the-submitdirect-sample"></a>SubmitDirect サンプルの要求 - 応答部分を実行するには  

1.  コマンド ウィンドウで、次のフォルダーに移動します。  

     \<*パスのサンプル*\>\AdaptersDevelopment\SubmitDirect\SubmitRequest\bin\Debug  

2.  ファイル SubmitRequest.exe を実行し、コマンド ラインで適切な .xml ファイル名を渡します。  

     例: SubmitRequest.\\..\DocInstance.xml  

3.  乗算演算の結果を含む応答 XML メッセージがコンソールに表示されることを確認します。  

## <a name="comments"></a>コメント  
 Submit アダプタは、他のアプリケーションでも使用できます。 このアダプターを任意の .NET ベースのコードから使用すると、プログラムで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを送信できます。 このアダプタをコードで使用するには、次の手順を実行します。  

#### <a name="to-use-the-sample-adapter-with-your-code"></a>サンプル アダプタをコードで使用するには  

1. Submit アダプターを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に登録します。 このサンプルで提供されているファイル Setup.bat を実行済みの場合、このアダプタは既に登録されて使用できる状態になっています。 それ以外の場合は、TransportProxyUtils.csproj、TransportProxyUtilsUI.csproj、および TransportProxyUtilsReg.csproj プロジェクトをビルドし、TransportProxyUtilsReg.csproj プロジェクトによって生成された実行可能ファイル RegisterAdapter.exe を実行するとアダプタを登録できます。  

   > [!IMPORTANT]
   >  BizTalk を 64 ビット コンピューターにインストールすると、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **RegisterAdapter.cs**ファイル。  

2. Submit アダプタを使用する受信場所を指定して、受信ポートを作成します。 受信場所のアドレスを指定します。 アドレスには、このアダプタを使用する受信場所内で一意の、任意の文字列を指定できます。  

3. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクト内でアセンブリ Microsoft.BizTalk.SDKSamples.AdaptersDevelopment.TransportProxyUtils.dll を参照します。  

4. このアセンブリによって提供される次のメソッドを 1 つ以上使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージを送信します。  


   |                                                メソッド                                                |                                                                                                                                                                                       説明                                                                                                                                                                                       |
   |---------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       **SubmitMessage()**<br /><br /> **BeginSubmitMessage()**<br /><br /> **EndSubmitMessage()**       |              一方向のメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信するための同期メソッドおよび非同期メソッドです。 メッセージが送信される受信場所のアドレスは、メッセージ コンテキストに設定する必要があります。<br /><br /> 送信の状態 (成功または失敗) を示すブール値が返されます。              |
   |     **SubmitMessages()**<br /><br /> **BeginSubmitMessages()**<br /><br /> **EndSubmitMessages()**      | 一方向のメッセージの配列を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信するための同期メソッドおよび非同期メソッドです。 メッセージが受信される受信場所のアドレスをメッセージのコンテキストで設定する必要があります。<br /><br /> 送信の状態 (成功または失敗) を示すブール値が返されます。 |
   | **SubmitSyncMessage()**<br /><br /> **BeginSubmitSyncMessage()**<br /><br /> **EndSubmitSyncMessage()** |                                     要求メッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信するための同期メソッドおよび非同期メソッドです。 メッセージが受信される受信場所のアドレスをメッセージ コンテキストで設定する必要があります。<br /><br /> 応答メッセージが返されます。                                      |
   |                                      **CreateMessageFromString()**                                      |                                                                     文字列から [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ オブジェクトを作成し、メッセージ コンテキストで受信場所のアドレスのプロパティを設定します。<br /><br /> BizTalk メッセージ オブジェクトを返します。                                                                      |
   |                                      **CreateMessageFromStream()**                                      |                                ストリームから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ オブジェクトを作成し、メッセージ コンテキストで受信場所のアドレスのプロパティを設定します。<br /><br /> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ オブジェクトを返します。                                |

    これらのメソッドのパラメータおよび戻り値の型の詳細については、TransportProxyUtils フォルダの MessagingAPIInterface.cs ファイルを参照してください。  

## <a name="see-also"></a>参照  
 [アダプタ サンプル - 開発](../core/adapter-samples-development.md)   
 [アダプターの登録](../core/registering-an-adapter.md)