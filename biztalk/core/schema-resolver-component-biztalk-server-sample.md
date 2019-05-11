---
title: スキーマ リゾルバ コンポーネント (BizTalk Server サンプル) |Microsoft Docs
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
ms.openlocfilehash: d34ef9109c95ae853c9d3b8319961a7c22d73628
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396911"
---
# <a name="schema-resolver-component-biztalk-server-sample"></a>スキーマ リゾルバ コンポーネント (BizTalk Server サンプル)
スキーマ リゾルバ コンポーネント サンプルは、の機能を拡張する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]フラット ファイル逆アセンブラー コンポーネントです。  
  
 通常、フラット ファイル逆アセンブラー コンポーネントではデザイン時に解析スキーマを定義する必要があります。 同じ受信場所で異なるフラット ファイル ドキュメントを受信する場合は、通常、受信パイプライン、スキーマごとに 1 つで複数のフラット ファイル逆アセンブラを含めます。 実行時に、パイプライン プローブ機能を使用して、適切な逆アセンブラ コンポーネントが選択されます。 ただし、この方法は多数のフラット ファイル スキーマがあるため、パイプラインのパフォーマンスが低下ごとの対応する逆アセンブラー コンポーネントのプローブに負荷がかかるです。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 スキーマ リゾルバ コンポーネントは、フラット ファイル逆アセンブラーのスキーマを選択した場合の代替方法を示します。 このサンプルで 4 つのスキーマが定義されているし、各スキーマのメッセージの最初の 2 つの文字が一意です。 一意の最初の 2 つの文字と、対応するスキーマの間のマッピングが定義されます。 スキーマ リゾルバ コンポーネントには、入力メッセージが指定された場合、最初の 2 つの文字を読み取り、対応するドキュメントを使用するスキーマが決定、メッセージ コンテキストにスキーマ情報を保存し、標準のフラット ファイルを呼び出す逆アセンブラー コンポーネントです。 標準のフラット ファイル逆アセンブラー コンポーネントは、メッセージ コンテキストからスキーマ情報を読み取るし、そのスキーマを使用して、ドキュメントの解析。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Pipelines\SchemaResolverComponent\  
  
 次の表では、このサンプルで使用されるファイルが表示され、その目的について説明します。  
  
|ファイル|説明|  
|---------------|-----------------|  
|SchemaResolverSample.sln|カスタム パイプライン コンポーネントを実行する BizTalk プロジェクトのソリューションです。|  
|SchemaResolverSample.btproj|カスタム パイプライン コンポーネントを実行する BizTalk プロジェクトです。|  
|SchemaResolverRP.btp|カスタム コンポーネントを含むパイプラインを受信します。|  
|PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd|フラット ファイル スキーマです。|  
|POInstance.txt、PRInstance.txt、SOInstance.txt、SRInstance.txt|対応するフラット ファイル ドキュメント インスタンスです。|  
|SchemaResolverFlatFileDasm.sln|パイプライン コンポーネントの実装のためのソリューションです。|  
|SchemaResolverFlatFileDasm.csproj|C#パイプライン コンポーネントの実装用のプロジェクト。|  
|SchemaResolverFlatFileDasmComp.cs|パイプライン コンポーネントの実装です。|  
|SeekableReadOnlyStream.cs|コンポーネントによって使用されるシーク可能な読み取り専用ストリームの実装です。|  
|VirtualStream.cs|パイプライン コンポーネントによって使用される仮想ストリームの実装です。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順を使用して、ビルドして、スキーマ リゾルバ コンポーネント サンプルを初期化します。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウでは、次のフォルダーにディレクトリ (cd) を変更します。  
  
     *\<パスのサンプル\>* \Pipelines\SchemaResolverComponent  
  
2.  ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
    -   コンポーネントをビルドします。  
  
    -   コンポーネント アセンブリを BizTalk \Pipeline components フォルダーにコピーします。  
  
    -   ビルドし、サンプル BizTalk プロジェクトをデプロイします。  
  
    -   受信場所と送信ポートを構成し、それらを開始します。  
  
    > [!NOTE]
    >  エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 スキーマ リゾルバ コンポーネント サンプルを実行するのにには、次の手順を使用します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  POInstance.txt、PRInstance.txt、SOInstance.txt、SRInstance.txt ファイルを受信場所にドロップ\<*インストール パス*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In  
  
2.  書き込まれた 4 つの .xml ファイルを確認、 \<Installdir\>\SDK\Samples\Pipelines\SchemaResolverComponent\Out フォルダ。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)