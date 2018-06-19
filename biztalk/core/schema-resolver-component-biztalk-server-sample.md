---
title: スキーマ リゾルバ コンポーネント (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], examples
- examples, schemas
- schemas, examples
- examples, Flat File Disassembler [pipeline component]
ms.assetid: 9ef68988-c4ee-42d5-83b5-a5c978b2007d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b59a0606b3cb30827078e28a89d0a51f52c430
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974920"
---
# <a name="schema-resolver-component-biztalk-server-sample"></a>スキーマ リゾルバ コンポーネント (BizTalk Server サンプル)
スキーマ リゾルバ コンポーネントのサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] フラット ファイル逆アセンブラ コンポーネントの機能を拡張する方法を示します。  
  
 フラット ファイル逆アセンブラ コンポーネントでは、通常デザイン時に解析スキーマを定義することが必要です。 そのため、同じ受信場所で異なるフラット ファイル ドキュメントを受信する場合は、受信パイプラインに複数のフラット ファイル逆アセンブラ (つまりスキーマごとに 1 つのフラット ファイル逆アセンブラ) を含めます。 実行時に、パイプライン プローブ機能を使用して、適切な逆アセンブラ コンポーネントが選択されます。 ただし、多数のフラット ファイル スキーマがある場合は、このアプローチのコストが高くなります。これは、対応するそれぞれの逆アセンブラ コンポーネントをプローブすることで、パイプラインのパフォーマンスが低下するためです。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 スキーマ リゾルバ コンポーネントは、フラット ファイル逆アセンブラ コンポーネントのスキーマを選択する、もう 1 つの方法を示します。 このサンプルでは、4 つのスキーマが定義されており、各スキーマのメッセージの最初の 2 文字は一意です。 一意である最初の 2 文字、および対応するスキーマの間でマッピングが定義されます。 入力メッセージがスキーマ リゾルバ コンポーネントに提供されると、最初の 2 文字が読み取られ、対応するドキュメントに使用するスキーマが決定されて、メッセージ コンテキストでスキーマ情報が保存された後に、標準のフラット ファイル逆アセンブラ コンポーネントが呼び出されます。 標準フラット ファイル逆アセンブラ コンポーネントはメッセージ コンテキストからスキーマ情報を読み取り、そのスキーマを使用してドキュメントを解析します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Pipelines\SchemaResolverComponent\  
  
 次の表は、このサンプルで使用したファイルを示し、その目的を説明しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|SchemaResolverSample.sln|カスタム パイプライン コンポーネントを実行する BizTalk プロジェクトのソリューション。|  
|SchemaResolverSample.btproj|カスタム パイプライン コンポーネントを実行する BizTalk プロジェクト。|  
|SchemaResolverRP.btp|カスタム コンポーネントを含む受信パイプライン。|  
|PurchaseOrder.xsd、PurchaseRequest.xsd、SalesOrder.xsd、SalesRequest.xsd|フラット ファイル スキーマ。|  
|POInstance.txt、PRInstance.txt、SOInstance.txt、SRInstance.txt|対応するフラット ファイル ドキュメント インスタンス。|  
|SchemaResolverFlatFileDasm.sln|パイプライン コンポーネントの実装のソリューション。|  
|SchemaResolverFlatFileDasm.csproj|パイプライン コンポーネントの実装の C# プロジェクト。|  
|SchemaResolverFlatFileDasmComp.cs|パイプライン コンポーネントの実装。|  
|SeekableReadOnlyStream.cs|コンポーネントで使用するシーク可能な読み取り専用ストリームの実装。|  
|VirtualStream.cs|パイプライン コンポーネントで使用する仮想ストリームの実装。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順を使用して、スキーマ リゾルバ コンポーネント サンプルをビルドおよび初期化します。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウで、ディレクトリを次のフォルダに変更します (cd)。  
  
     *\<パスのサンプル\>* \Pipelines\SchemaResolverComponent  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   コンポーネントをビルドします。  
  
    -   コンポーネント アセンブリを BizTalk \Pipeline \Pipeline components フォルダにコピーします。  
  
    -   サンプル BizTalk プロジェクトをビルドして展開します。  
  
    -   受信場所と送信ポートを構成し、それらを開始します。  
  
    > [!NOTE]
    >  このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順を使用して、スキーマ リゾルバ コンポーネント サンプルを実行します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  POInstance.txt、PRInstance.txt、SOInstance.txt、および SRInstance.txt ファイルを受信場所にドロップ\<*インストール パス*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In  
  
2.  書き込まれた 4 つの .xml ファイルを確認、 \<Installdir\>\SDK\Samples\Pipelines\SchemaResolverComponent\Out フォルダです。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)