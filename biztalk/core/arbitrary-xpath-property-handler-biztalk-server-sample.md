---
title: 任意の XPath プロパティ ハンドラ (BizTalk Server サンプル) |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f2f59ce48a3d46ebf33889e31a55f9aa452fd17
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="arbitrary-xpath-property-handler-biztalk-server-sample"></a>任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)
任意の XPath プロパティ ハンドラー ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サンプル) では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信される XML ドキュメント上で特定のプロパティを昇格させるためのカスタム パイプライン コンポーネントを記述する方法を示します。 サンプルに含まれる機能を使用して、XPath 式を評価する通常、アセンブラ、および逆アセンブラの各カスタム コンポーネントを作成できます。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルには、処理する注文書 (PO) XML ドキュメント DocInstance.xml が含まれています。 このサンプルでは、次の手順で DocInstance.xml を処理します。  
  
1.  DocInstance.xml は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信ポートによって取得され、任意の XPath プロパティ ハンドラーというカスタム パイプライン コンポーネントによって処理されます。  
  
2.  任意の XPath プロパティ ハンドラ コンポーネントはすべてを昇格\<価格\>と\<数量\>として任意の XPath 式を持つ要素が、PO スキーマで定義します。 XPath 式には、PO ドキュメントのルート要素のあいまいな子要素で使用される位置コンストラクタも含まれています。  
  
3.  任意の XPath プロパティ ハンドラ コンポーネントはメッセージの種類を判断し、メッセージ コンテキストに昇格させます。  
  
4.  次に、その後の処理のために、昇格する要素を持つ XML ドキュメントをオーケストレーションに送信します。  
  
5.  オーケストレーションは、PO ドキュメント内の昇格する要素にアクセスし、PO 内の項目の合計数を計算します。  
  
6.  オーケストレーションは、元の PO と更新された合計の両方からの情報を含む新しい PO ドキュメントを作成します。  
  
7.  新しい PO ドキュメントは、\Output ディレクトリのファイルに書き込まれます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<Samples Path\>*\Pipelines\ArbitraryXPathPropertyHandler  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|ArbitraryXPathPropertyHandler.sln|カスタムのパイプライン コンポーネント ソリューション ファイルです。|  
|ArbitraryXPathPropertyHandler.resX|リソース ファイルです。|  
|ArbitraryXPathPropertyHandlerComp.cs|主要なコンポーネント実装です。|  
|AssemblyInfo.cs|アセンブリ情報です。|  
|Cleanup.bat|サンプルのクリーンアップ ファイル。|  
|PromotingMap.cs|ネイティブの CLR 型マップ実装としてのプロパティの昇格です。|  
|PropertyAttributes.cs|カスタム属性、プロパティ記述子、および ICustomTypePropertyDescriptor 実装です。|  
|SchemaMap.cs|スキーマのあいまいさを解決するための、メッセージの種類から IDocumentSpec へのスキーマ マッピングです。|  
|Setup.bat|サンプル パイプライン コンポーネントをビルドおよび設定します。|  
|VirtualStream.cs|仮想ストリームの実装です。|  
|SeekableReadOnlyStream.cs|シーク可能な読み取り専用ストリームの実装です。|  
|ArbitraryXPathSample.sln|サンプルのオーケストレーション ソリューション ファイルです。|  
|CalculateTotalAmount.odx|サンプルのオーケストレーションです。|  
|PODocument.xsd|注文書スキーマ。|  
|DocInstance.xml|サンプルの注文書インスタンスです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 このサンプルは、同じコンピューターで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が実行されている [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 環境で実行するように設計されています。 環境がこの構成と異なる場合は、正しい SQL Server コンピューターを指定するように、任意の XPath プロパティ ハンドラー ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サンプル) を変更する必要があります。  
  
> [!IMPORTANT]
>  Setup.bat は、Microsoft Windows のインストール ディレクトリが C:\Windows であることを前提にしています。 Windows のインストールが別のディレクトリの場合は、グローバル アセンブリ キャッシュの Microsoft.BizTalk.Component.Utilities アセンブリの場所を反映するように、ArbitraryXPathPropertyHandler.csproj ファイルを変更する必要があります。 参照要素で、次のように変更します。 \<SYSTEMROOT\> Windows がインストールされている場所に (たとえば、C:\WINNT\\)。  
  
```  
<Reference  
  Name = "Microsoft.BizTalk.Component.Utilities"  
  AssemblyName = "Microsoft.BizTalk.Component.Utilities"  
  HintPath = "<SYSTEMROOT>\assembly\GAC\Microsoft.BizTalk.Component.Utilities\3.0.1.0__31bf3856ad364e35\Microsoft.BizTalk.Component.Utilities.dll"  
/>  
```  
  
 次の手順を使用して、任意の XPath プロパティ ハンドラー ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サンプル) の作成および初期化を行います。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーにします。  
  
     *\<Samples Path\>*\Pipelines\ArbitraryXPathPropertyHandler  
  
2.  ファイル Setup.bat では、次の操作を実行しますが、実行します。  
  
    -   任意の XPath プロパティ ハンドラ パイプライン コンポーネントをビルドします。  
  
    -   構築されたコピーのパイプライン コンポーネントを*\<インストール パス\>*\Pipeline Components ディレクトリ。  
  
    -   送信ポートおよび受信ポートを作成します。  
  
    -   サンプルで使用される入力ディレクトリと出力ディレクトリを作成します。  
  
    -   サンプルの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーション ArbitraryXPathSample をインストールします。  
  
    -   ポートをサンプル オーケストレーションにバインドします。  
  
    -   オーケストレーションを開始します。  
  
    > [!NOTE]
    >  ビルドおよび初期化中にエラーが報告されることはありません。 エラーが発生した場合は、必要なソフトウェアがすべてインストールされ、パスで Microsoft ビルド ツールが使用できることを確認してください。  
  
    > [!NOTE]
    >  Setup.bat が行った変更を元に戻すには、まず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでホスト インスタンスを停止し、再起動する必要があります。 次に、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順を使用して、任意の XPath プロパティ ハンドラー ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サンプル) を実行します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  注文書 (PO) ファイル DocInstance.xml を \Input ディレクトリにコピーします。 PO ファイルは受信ポートによって取得されます。受信ポートは、XML データを任意の XPath プロパティ ハンドラ パイプライン コンポーネントに送信します。  
  
2.  \Output ディレクトリの内容を表示します。 \Input ディレクトリにコピーした DocInstance.xml ファイルのすべての情報を含む新しいファイルが作成されています。 される点が異なりますファイルのようになりました、 \<TotalAmount\> PO の合計容量を持つ要素が設定されています。  
  
## <a name="comments"></a>コメント  
 正規 XPath 式などの単純式は、"/* [ローカル名 () '要素名' と namespaceURI() を = ='http://MyUri.org']/\*[ローカル名 () =' 要素名 ']/@\*[ローカル名 =' 属性名 ']"です。  
  
 任意の XPath 式は、"//element-name//*[local-name()='element-name' and position()=2]" のように複雑な場合があります。 実際は、XPath ボディまたは XPath プロパティで使用される非正規 XPath がスキーマに含まれる場合に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では非正規 XPath 式はサポートされていないという実行時エラーが発生します。 任意の XPath 式をサポートできるようにするには、任意の XPath ボディと任意の XPath プロパティ式の両方をサポートするカスタムの逆アセンブラおよびアセンブラ コンポーネントを作成します。  
  
 このサンプルでは、カスタム パイプライン コンポーネントで、次の一連の手順を使用時に **IComponent.Execute** 実装されます。  
  
1.  入力メッセージのボディ部ストリームで仮想のシーク可能ストリームを作成します (入力メッセージが大きく、ストリームをシークできない可能性があるため、メモリ使用量を少なくし、ストリーム位置を変更できるようにします)。  
  
2.  新しい送信メッセージ、およびメッセージの新しいボディ部を作成し、仮想ストリームを新しいボディ部に割り当て、ボディ部のプロパティのクローンを作成し、メッセージ コンテキストのクローンを作成します。  
  
3.  入力メッセージ、またはデザイン時に指定されたスキーマに基づいて、スキーマを取得します。  
  
4.  インスタンスに、ストリームを読み込みます **System.Xml.XmlDocument**します。  
  
5.  昇格させたプロパティと識別フィールドを処理し、送信メッセージのメッセージ コンテキストへの昇格または書き込みを行います。  
  
6.  送信メッセージを返します。  
  
7.  送信メッセージをファイルに書き込みます。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)