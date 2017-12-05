---
title: "HTTPSolicitResponse |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: b149544e-3279-4ac9-b31f-fff3e41ec8e7
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 500ec05df9a3a365a350571e8b3e66f5d584f92d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="httpsolicitresponse"></a>HTTPSolicitResponse
HTTPSolicitResponse サンプルは、オーケストレーション データの処理に ASP.NET アプリケーションを利用する Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを作成する方法を示します。 このサンプルでは、オーケストレーションは要求 - 応答のポートを利用して、ASP.NET アプリケーションにメッセージを送信し、応答を受信します。 HTTP アダプターを使用することにより、BizTalk Server オーケストレーションと ASP.NET アプリケーションを統合できます。 詳細については、次を参照してください。 [HTTP アダプター](../core/http-adapter.md)です。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、以下の手順で、乗算する 2 つの数値を含んでいる要求を受信し、その要求に応答する BizTalk Server オーケストレーションを提供します。  
  
1.  BizTalk Server オーケストレーションが、特定のフォルダーから .xml 入力ファイルを取得します。  
  
2.  次に、BizTalk Server オーケストレーションは、HTTP 要求を使用して、.xml 入力ファイルからマルチプライア ASP.NET アプリケーションに XML を転送します。  
  
3.  マルチプライア ASP.NET アプリケーションが、乗算を実行し、HTTP 応答で結果を XML として返すことにより、HTTP 要求に応答します。  
  
4.  BizTalk Server オーケストレーションが、HTTP 応答で結果を XML として受信し、特定のフォルダーの .xml ファイルに結果を書き込みます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\AdaptersUsage\HTTPSolicitResponse  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Cleanup.bat|必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。|  
|HttpSolicitResponse.btproj、HttpSolicitResponse.sln|マルチプライア ASP.NET アプリケーションや関連スキーマなどを使用するオーケストレーションを含む BizTalk プロジェクトのプロジェクト ファイルとソース ファイルを提供します。|  
|HttpSolicitResponseBinding.xml|ポートのバインドなどの自動化されたセットアップを可能にします。|  
|MultiplyRequest.xsd、MultiplyResponse.xsd|MultiplyRequest.xsd は乗算要求、MultiplyResponse.xsd は乗算応答の XML メッセージのスキーマを提供します。|  
|MultiplyTwoIntegers.odx|乗算演算を要求する .xml ファイルを受信し、その要求をマルチプライア ASP.NET アプリケーションに転送してから、その応答を .xml ファイルに書き込む BizTalk Server オーケストレーションを提供します。|  
|request_in.xml|サンプル入力ファイルです。|  
|Setup.bat|このサンプルを作成および初期化します。|  
|\Multiplier フォルダー内のファイル: <br /><br /> Multiplier.aspx, Multiplier.aspx.cs, Multiplier.sln|マルチプライア サービスを実装する ASP.NET アプリケーションを構成するファイル (プロジェクト ファイルとソリューション ファイル、ASPX ファイル、Microsoft Visual C# .NET ソース ファイルなど) を含みます。|  
  
## <a name="building-and-initializing-the-sample"></a>サンプルのビルドおよび初期化  
 次の手順に従って、HTTPSolicitResponse サンプルをビルドおよび初期化します。  
  
> [!NOTE]
>  受信場所の名前に大文字が含まれている場合、このサンプルは機能しません。  
  
#### <a name="to-build-and-initialize-the-sample"></a>このサンプルをビルドおよび初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\AdaptersUsage\HTTPSolicitResponse  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   このサンプルで使用する入力フォルダーと出力フォルダーを作成します。  
  
         \<*パスのサンプル*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput  
  
         \<*パスのサンプル*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput  
  
    -   このサンプルで使用するマルチプライア ASP.NET アプリケーションをコンパイルして構成します。  
  
        > [!NOTE]
        >  IIS マネージャーでアプリケーション プールを作成中に次のように設定します。、 **DefaultAppPool** .NET Framework バージョンを**.Net Framework v4.0**です。  
  
    -   このサンプルで使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをコンパイルし、展開します。  
  
    -   必要な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所およびポートを作成してバインドします。  
  
        > [!NOTE]
        >  このサンプルは、ポートを作成してバインドする際に、以下の警告を表示します。  
  
        > [!NOTE]
        >  `Warning: Receive handler not specified for receive location "HttpSolicitResponseReceiveLocation"; updating with first receive handler with matching transport type.`  
  
        > [!NOTE]
        >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.HttpSolicitResponse.MultiplyTwoIntegers"; updating with first available host.`  
  
    -   受信場所を有効にし、送信ポートを開始します。  
  
        > [!NOTE]
        >  このサンプルのオーケストレーションは、ASP.NET アプリケーションとの HTTP 通信に双方向ポートを使用します。  
  
        > [!NOTE]
        >  このサンプルを実行する前に、BizTalk がビルド プロセス中および初期化プロセス中にエラーを報告していないことを確認してください。  
  
        > [!NOTE]
        >  開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
  
        > [!NOTE]
        >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-the-sample"></a>サンプルを実行します。  
 次の手順に従って、HTTPSolicitResponse サンプルを実行します。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  request_in.xml ファイルのコピーを HttpSolicitResponseInput フォルダーに貼り付けます。  
  
2.  .xml ファイルが HttpSolicitResponseOutput フォルダーに作成されたことを確認します。 この .xml ファイルの名前はメッセージ ID GUID に基づいて付けられます。 このファイルには、乗算演算の XML 形式の結果が含まれています。  
  
    > [!NOTE]
    >  入力ファイルのオペランド値を変更すると、異なる乗算演算を実行できます。  
  
## <a name="comments"></a>コメント  
 このサンプルは、HTTP インターフェイスを公開する異なる外部システムと通信するようにカスタマイズできます。  
  
 MultiplyRequest.xsd ファイルと MultiplyResponse.xsd ファイルは、それぞれ、マルチプライア ASP.NET アプリケーションの入力データおよび出力データの形式を定義する XML スキーマです。 オーケストレーションは、これらのファイルを使用して要求メッセージと応答メッセージの種類を定義します。  
  
## <a name="see-also"></a>参照  
 [HTTP アダプター サンプル](../core/http-adapter-samples.md)