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
ms.openlocfilehash: dce1313fd851d04a490a31b602611072ade2242d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396055"
---
# <a name="submitdirect-biztalk-server-sample"></a>SubmitDirect (BizTalk Server サンプル)
SubmitDirect サンプル プログラムで、一方向送信する方法と要求/応答メッセージを Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]から。NET ベースのアプリケーション。 サンプルの使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アダプター Api。 メッセージを送信するために使用できる、Submit という名前の受信アダプターも用意されています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  

## <a name="prerequisites"></a>前提条件  
 このサンプルを実行する前に、BizTalk 分離ホスト ユーザー グループに属するユーザーとしてログオンしていることを確認します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、BizTalk アダプターに関連するさまざまなタスクを実行する方法を示します。 具体的には、表示する方法。  

- 外部で実行される分離アダプターの動作、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス。 外部プロセスによって作成されるので、送信アダプターは分離アダプター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセス (起動する .NET アプリケーションとして)。  

- メッセージのバッチを送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 Submit アダプタは、一度に複数のメッセージを送信するのにバッチ メッセージ送信機能を使用します。  

- 同期的に、要求/応答パラダイムを使用して、非同期的に一方向パラダイムを使用してメッセージを送信します。  

- 登録のアダプターが[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このサンプルでは、アダプターを登録する方法を示していて、アダプターの登録を自動化する登録実行可能ファイルを提供します。  

  このサンプルでは、1 つは、実際には 2 つのサンプルをとおりです。  

- **一方向のメッセージのバッチを送信します。** コンソール アプリケーション SubmitMessages.exe は、コマンドラインから文字列を受け取るし、それぞれを別々 のメッセージとして送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 メッセージは、受信場所で取得が送信された各[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、パススルー受信パイプラインおよび送信パイプラインを通じて送信され、テキスト ファイルに書き込まれます。  

- **要求/応答メッセージの送信。** コンソール アプリケーション SubmitRequest.exe はコマンドラインで指定された .xml ファイルを受け取るし、それに送信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 この .xml ファイルのスキーマでは、2 つの整数フィールドが含まれている要素を定義します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .xml ファイルを取得し、それを (1 つの要求/応答のポート) を使用したオーケストレーションによって処理します。 マップを使用して、要求で 2 つの整数の積である整数を返す XML 応答メッセージを生成します。 コンソール アプリケーションは、応答を受信すると、結果が表示されます。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect\  

 次の表では、このサンプルではファイルの一覧し、その目的について説明します。  


|                                                                                                                     ファイル                                                                                                                      |                                                                                              説明                                                                                               |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                   Cleanup.bat                                                                                                                    |    必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。    |
|                                                                                                                    Setup.bat                                                                                                                     |                                                                                  このサンプルを作成および初期化します。                                                                                   |
|                                                                                                                 SubmitDirect.sln                                                                                                                 |                                ProcessRequest フォルダと Microsoft Visual で BizTalk プロジェクトを含むソリューション ファイルC#他のフォルダー内のプロジェクト。                                 |
|                                                                                               SubmitMessagesBinding.xml, SubmitRequestBinding.xml                                                                                                |                                                                             ポートのバインドなど、自動化されたセットアップに使用されます。                                                                             |
|                                                              \ProcessRequest フォルダー。<br /><br /> DocIn.xsd, DocOut.xsd, Multiplier.odx, Multiply.btm, ProcessRequest.btproj                                                               |                                               要求/応答シナリオで整数の乗算を実行する BizTalk プロジェクトを提供します。                                                |
|                                                                       \SubmitMessages フォルダー。<br /><br /> AssemblyInfo.cs, SubmitMessages.cs, SubmitMessages.csproj                                                                       |                                ビジュアルを提供します。C#を別々 のメッセージのバッチとしてそのコマンドライン文字列パラメータを渡すコンソール アプリケーション用のプロジェクト。                                |
|                                                                In the \SubmitRequest folder:<br /><br /> AssemblyInfo.cs, DocInstance.xml, SubmitRequest.cs, SubmitRequest.csproj                                                                |                                 提供、C#を乗算する 2 つの整数を含む .xml ファイル (DocInstance.xml) を渡すコンソール アプリケーション用のプロジェクト。                                 |
| \TransportProxyUtils フォルダー。<br /><br /> AssemblyInfo.cs, MessageHelper.cs, MessagingAPIInterface.cs, MessagingAPIs.cs, ResponseCallBack.cs, TpBatchAsyncCallback.cs, TpBatchAsyncResult.cs, TpBatchStatus.cs, TransportProxyUtils.csproj | 提供、 C# 、同期および非同期メッセージを送信し、バッチおよび 1 つの要求メッセージの送信メソッドを実装する送信アダプターのランタイム部分のプロジェクト。 |
|                                                              \TransportProxyUtilsReg フォルダー。<br /><br /> AssemblyInfo.cs, RegisterAdapter.cs, TransportProxyUtilsReg.csproj                                                               |           ビジュアルを提供します。C#アダプターを登録するために使用できるコードを示すプロジェクト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。           |
|                                                           \TransportProxyUtilsUI フォルダー。<br /><br /> AssemblyInfo.cs, TransportProxyUtilsMgmt.cs, TransportProxyUtilsUI.csproj                                                            |                                                           ビジュアルを提供します。 C# Submit アダプタのユーザー インターフェイス部分のプロジェクト。                                                           |

## <a name="building-and-initializing-the-sample"></a>サンプルのビルドおよび初期化  

#### <a name="to-build-and-initialize-the-submitdirect-sample"></a>ビルドして、SubmitDirect サンプルの初期化  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - このサンプルのバッチ送信部分の次の出力フォルダーを作成します。  

      \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect\Out  

   - さまざまなコンパイル[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。  

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

   - 受信場所を使用し、送信ポートおよびオーケストレーションを開始します。  

     > [!NOTE]
     >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
     > 
     > [!NOTE]
     >  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
     > 
     > [!NOTE]
     >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

## <a name="running-the-sample"></a>サンプルを実行します。  
 このサンプルでは、ファイル アダプターを使用するためには、BizTalk ホスト (BizTalkServerApplication) を実行する必要があります。 SubmitDirect サンプルを実行するのにには、次の手順を使用します。  

#### <a name="to-run-the-batch-submission-portion-of-the-submitdirect-sample"></a>SubmitDirect サンプルのバッチ送信部分を実行するには  

1.  コマンド ウィンドウで、次のフォルダーに移動します。  

     \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect\SubmitMessages\bin\Debug  

2.  ファイル SubmitMessages.exe、コマンドラインで複数の文字列を渡すことを実行します。  

     例:SubmitMessages msg1 msg2 msg3  

3.  Out 出力フォルダに作成された複数のテキスト ファイルを確認します。これらのファイルには、ファイルごとに 1 つのコマンド ラインで渡された文字列が含まれます。  

#### <a name="to-run-the-requestresponse-portion-of-the-submitdirect-sample"></a>SubmitDirect サンプルの要求/応答の部分を実行するには  

1.  コマンド ウィンドウで、次のフォルダーに移動します。  

     \<*Samples Path*\>\AdaptersDevelopment\SubmitDirect\SubmitRequest\bin\Debug  

2.  ファイル SubmitRequest.exe、コマンドラインで、適切な .xml ファイル名を渡すことを実行します。  

     例:SubmitRequest ..\\..\DocInstance.xml  

3.  コンソールに表示される乗算演算の結果を含む応答 XML メッセージを確認します。  

## <a name="comments"></a>コメント  
 Submit アダプタは、その他のアプリケーションで使用できます。 いずれかから使用できます。NET ベースのコードにメッセージを送信、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プログラムを使用します。 で、コードをこのアダプターを使用するには、次の手順を使用します。  

#### <a name="to-use-the-sample-adapter-with-your-code"></a>サンプル アダプターをコードで使用するには  

1. Submit アダプターを登録、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このサンプルに付属する Setup.bat ファイルを実行する場合、アダプターが登録され、使用する準備になります。 それ以外の場合、TransportProxyUtils.csproj、TransportProxyUtilsUI.csproj、および TransportProxyUtilsReg.csproj プロジェクトをビルドし、プロジェクト、RegisterAdapter.exe によって生成された実行可能ファイルを実行して登録できます。  

   > [!IMPORTANT]
   >  BizTalk を 64 ビット コンピューターにインストールすると、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **RegisterAdapter.cs**ファイル。  

2. Submit アダプタを使用する受信場所と受信ポートを作成します。 受信場所のアドレスを指定します。 アドレスは、このアダプターを使用する受信場所内で一意である任意の文字列を指定できます。  

3. アセンブリ Microsoft.BizTalk.SDKSamples.AdaptersDevelopment.TransportProxyUtils.dll を参照で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクト。  

4. メッセージを送信、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]このアセンブリによって提供される次のメソッドの 1 つ以上を使用しています。  


   |                                                メソッド                                                |                                                                                                                                                                                       説明                                                                                                                                                                                       |
   |---------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       **SubmitMessage()**<br /><br /> **BeginSubmitMessage()**<br /><br /> **EndSubmitMessage()**       |              同期および非同期のメソッドに一方向のメッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 メッセージが送信される受信場所のアドレスは、メッセージ コンテキストに設定する必要があります。<br /><br /> 送信 (成功/失敗) の状態を示すブール値が返されます。              |
   |     **SubmitMessages()**<br /><br /> **BeginSubmitMessages()**<br /><br /> **EndSubmitMessages()**      | 同期および非同期のメソッドに一方向のメッセージの配列を送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 メッセージのコンテキストでは、メッセージが受信する受信場所のアドレスを設定してください。<br /><br /> 送信 (成功/失敗) の状態を示すブール値が返されます。 |
   | **SubmitSyncMessage()**<br /><br /> **BeginSubmitSyncMessage()**<br /><br /> **EndSubmitSyncMessage()** |                                     同期および非同期のメソッドを要求を送信するメッセージを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 メッセージ コンテキストでメッセージが送信される受信場所のアドレスを設定する必要があります。<br /><br /> 応答メッセージが返されます。                                      |
   |                                      **CreateMessageFromString()**                                      |                                                                     作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文字列からオブジェクトをメッセージおよびメッセージのコンテキストで受信場所のアドレスのプロパティを設定します。<br /><br /> BizTalk メッセージ オブジェクトを返します。                                                                      |
   |                                      **CreateMessageFromStream()**                                      |                                作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ オブジェクトをストリームからメッセージ コンテキストで受信場所のアドレスのプロパティを設定するとします。<br /><br /> 返します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ オブジェクト。                                |

    詳細については、パラメーターおよびこれらのメソッドの戻り値の型は、TransportProxyUtils フォルダの MessagingAPIInterface.cs ファイルを参照してください。  

## <a name="see-also"></a>参照  
 [アダプタ サンプル - 開発](../core/adapter-samples-development.md)   
 [アダプターの登録](../core/registering-an-adapter.md)