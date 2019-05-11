---
title: 任意の XPath プロパティ ハンドラ (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
ms.assetid: 4eb26c38-5ece-42b0-a28e-73214df1dc41
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b66ae9dd0149e8172726ff882de11dcf35ba25
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528587"
---
# <a name="arbitrary-xpath-property-handler-biztalk-server-sample"></a>任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)
任意の XPath プロパティ ハンドラ ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サンプル) に送信される XML ドキュメントの特定のプロパティを昇格させるためのカスタム パイプライン コンポーネントを記述する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 サンプルに含まれる機能を使用して、XPath 式を評価するカスタムの正規表現、アセンブラー、および逆アセンブラー コンポーネントを作成することができます。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 サンプルには、プロセス、DocInstance.xml を発注書 (PO) XML ドキュメントが含まれています。 サンプルでは、DocInstance.xml を処理する次の手順を使用します。  
  
1. DocInstance.xml はによって取得、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信ポートと、任意の XPath プロパティ ハンドラというカスタム パイプライン コンポーネントによって処理されます。  
  
2. 任意の XPath プロパティ ハンドラ コンポーネントはすべてを昇格\<価格\>と\<数量\>として任意の XPath 式を持つ要素は、PO スキーマで定義されています。 XPath 式には、PO ドキュメントのルート要素のあいまいな子要素で使用される位置コンストラクタも含まれています。  
  
3. 任意の XPath プロパティ ハンドラ コンポーネントは、メッセージの種類を決定し、メッセージ コンテキストに昇格させます。  
  
4. 次に、コンポーネントは、オーケストレーションをさらに処理するために、昇格する要素を持つ XML ドキュメントを送信します。  
  
5. オーケストレーションは、PO ドキュメントで昇格させた要素にアクセスし、PO 内の項目の合計数を計算します。  
  
6. オーケストレーションは、元の PO と更新された合計から情報を含む新しい PO ドキュメントを作成します。  
  
7. 新しい PO ドキュメントは、\Output ディレクトリのファイルに書き込まれます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Pipelines\ArbitraryXPathPropertyHandler  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|ArbitraryXPathPropertyHandler.sln|カスタム パイプライン コンポーネント ソリューション ファイルです。|  
|ArbitraryXPathPropertyHandler.resX|リソース ファイル。|  
|ArbitraryXPathPropertyHandlerComp.cs|主要なコンポーネントの実装。|  
|AssemblyInfo.cs|アセンブリ情報です。|  
|Cleanup.bat|サンプルのクリーンアップ ファイル。|  
|PromotingMap.cs|ネイティブの CLR 型としてプロパティの昇格では、実装をマップします。|  
|PropertyAttributes.cs|カスタム属性、プロパティ記述子、および ICustomTypePropertyDescriptor 実装です。|  
|SchemaMap.cs|スキーマのマッピングは、メッセージの種類から IDocumentSpec スキーマのあいまいさを解決します。|  
|Setup.bat|ビルドおよび設定のサンプル パイプライン コンポーネント。|  
|VirtualStream.cs|仮想ストリームの実装。|  
|SeekableReadOnlyStream.cs|シーク可能な読み取り専用ストリームの実装。|  
|ArbitraryXPathSample.sln|サンプル オーケストレーション ソリューション ファイルです。|  
|CalculateTotalAmount.odx|サンプル オーケストレーションです。|  
|PODocument.xsd|注文書スキーマ。|  
|DocInstance.xml|サンプルの注文書インスタンス。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 このサンプルがで実行するように設計、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]同じマシンで実行されています。 環境内でこの構成が一致しない場合は、任意の XPath プロパティ ハンドラーを変更する必要があります ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サンプル) を適切な SQL Server コンピューター をポイントします。  
  
> [!IMPORTANT]
>  Setup.bat では、Microsoft Windows のインストール ディレクトリが C:\Windows 前提としています。 Windows のインストールが別のディレクトリにある場合は、グローバル アセンブリ キャッシュの Microsoft.BizTalk.Component.Utilities アセンブリの場所を反映するように、ArbitraryXPathPropertyHandler.csproj ファイルを変更する必要があります。 参照要素では、次のように変更します。 \<SYSTEMROOT\> Windows がインストールされている場所に (たとえば、C:\WINNT\\)。  
  
```  
<Reference  
  Name = "Microsoft.BizTalk.Component.Utilities"  
  AssemblyName = "Microsoft.BizTalk.Component.Utilities"  
  HintPath = "<SYSTEMROOT>\assembly\GAC\Microsoft.BizTalk.Component.Utilities\3.0.1.0__31bf3856ad364e35\Microsoft.BizTalk.Component.Utilities.dll"  
/>  
```  
  
 次の手順を使用してビルドして、任意の XPath プロパティ ハンドラーを初期化 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サンプル)。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1. コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。  
  
    *\<パスのサンプル\>* \Pipelines\ArbitraryXPathPropertyHandler  
  
2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
   - 任意の XPath プロパティ ハンドラ パイプライン コンポーネントをビルドします。  
  
   - 構築されたコピーのパイプライン コンポーネントを*\<インストール パス\>* \Pipeline Components ディレクトリ。  
  
   - ポートと受信ポート、送信を作成します。  
  
   - このサンプルで使用される入力と出力ディレクトリを作成します。  
  
   - サンプル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション arbitraryxpathsample をインストールします。  
  
   - サンプル オーケストレーションにポートをバインドします。  
  
   - オーケストレーションを開始します。  
  
   > [!NOTE]
   >  ビルドおよび初期化中にエラーを報告しない必要があります。 エラーが発生した場合は、インストールされているすべての必要なソフトウェアがあることと、Microsoft ビルド ツールは、パスで使用できることを確認します。  
   > 
   > [!NOTE]
   >  Setup.bat による変更を元に戻したりするにはまず停止してから、ホスト インスタンスを再起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 次に、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順を使用して、任意の XPath プロパティ ハンドラを実行する ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サンプル)。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  注文書 (po) ファイル DocInstance.xml を \Input ディレクトリにコピーします。 PO ファイルは、任意の XPath プロパティ ハンドラ パイプライン コンポーネントに XML データを送信する受信ポートによって取得されます。  
  
2.  \Output ディレクトリの内容を表示します。 新しいファイルが作成 \Input ディレクトリにコピーした DocInstance.xml ファイルからのすべての情報を格納することに注意してください。 ファイルの違いは今すぐ、 \<TotalAmount\>要素に PO の合計量に設定されています。  
  
## <a name="comments"></a>コメント  
 正規 XPath 式の単純な式として"/* [ローカル名 () =' 要素名 ' と namespaceURI() ='http://MyUri.org']/\*[ローカル名 () =' 要素名 ']/@\*[ローカル名 =' 属性名 ']"。  
  
 任意の XPath 式はくらい複雑であることができます"//element-name//* [ローカル名 () 'の要素名' と位置 () = = 2]"。 実際、受け取りますで非正規 XPath 式がサポートされていないことを示す実行時エラー [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] XPath ボディまたは XPath プロパティで使用される非正規 XPath がスキーマにある場合。 任意の XPath 式をサポートするために、ソリューションでは、任意の XPath ボディと任意の XPath プロパティ式をサポートするカスタム逆アセンブラーおよびアセンブラー コンポーネントを作成します。  
  
 このサンプルは、カスタム パイプライン コンポーネントで、次の一連の手順を使用してとき**IComponent.Execute**実装されます。  
  
1.  入力メッセージのボディ パーツ ストリームに対して仮想のシーク可能ストリームを作成します。 (入力メッセージが大きくなることができます、ストリームをシーク可能ではないことができるためにする必要があります最小メモリ フット プリントがあるおよびストリームの位置を変更できる。)  
  
2.  そのため、新しい送信メッセージと新しいボディ部を作成、仮想ストリームを新しいボディ部に割り当てます、ボディ部のプロパティのクローンを作成およびメッセージ コンテキストのクローンを作成します。  
  
3.  デザイン時に指定されたスキーマに基づいて、入力メッセージのスキーマを取得します。  
  
4.  インスタンスに、ストリームを読み込みます**System.Xml.XmlDocument**します。  
  
5.  昇格させたプロパティと識別フィールドについて説明しますと昇格または送信メッセージのメッセージ コンテキストに書き込みます。  
  
6.  送信メッセージを返します。  
  
7.  送信メッセージをファイルに書き込みます。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)