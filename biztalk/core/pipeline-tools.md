---
title: "パイプライン ツール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline tools, XMLAsm.exe
- pipeline tools, FFDasm.exe
- Pipeline.exe
- FFDasm.exe
- pipeline tools, XMLDasm.exe
- pipeline tools
- XMLAsm.exe
- pipeline tools, DSDump.exe
- FFAsm.exe
- pipeline tools, FFAsm.exe
- pipeline tools, how to
- pipeline tools, about pipeline tools
- pipeline tools, Pipeline.exe
- utilities, pipeline tools
- XMLDasm.exe
ms.assetid: ca4d053a-1473-4d40-8cd0-1ed3a3af988a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c567ea50f151f0ee36505bd6d8a71af059eb67d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="pipeline-tools"></a>パイプライン ツール
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソフトウェア開発キット (SDK) 付属のパイプライン ツールを使用すると、送信ポートや受信ポートなどの BizTalk Server 環境を構成することなく、パイプラインが正しく機能するかどうかを確認できます。 パイプライン ツールは次の用途にも使用できます。  
  
-   サード パーティのパイプライン コンポーネントを、サーバー環境外でデバッグします。  
  
-   解析エンジンのエラー メッセージを診断します。  
  
-   コンパイル、展開、展開解除、および再コンパイルを行うことなく、さまざまなスキーマをテストします。  
  
-   フラット ファイルおよび XML のアセンブラー/逆アセンブラーの動作を検討します。  
  
-   逆アセンブラーの出力を表示し、昇格したメッセージ コンテキスト プロパティとその値を確認します。  
  
-   逆アセンブラー コンポーネントやアセンブラー コンポーネントが含まれない送受信パイプラインを実行します (たとえば、S/MIME デコーダーの出力を表示できます)。  
  
-   メッセージング サブシステム全体ではなく、パイプラインのみに対し、詳細なパフォーマンス測定を行います。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*インストール パス*\>\SDK\Utilities\PipelineTools  
  
 パイプライン ツールは、パイプラインとパイプライン コンポーネント (フラット ファイルおよび XML のアセンブラー/逆アセンブラー コンポーネント) の実行、デバッグ、およびプロファイルに使用します。  
  
## <a name="file-inventory"></a>ファイルのインベントリ  
 次の表は、パイプライン ツールのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|DSDump.exe|ドキュメント スキーマ構造をダンプするために使用します。この構造は、1 つ以上の XSD スキーマのメモリ内簡易表現で、フラット ファイルの注釈を含む場合と含まない場合があります。 $Root$0$3$2 などの解析エンジン エラーが発生し、デコードする必要がある場合に、このツールが役立ちます。 $ 後の数値は、ドキュメント スキーマに表示される、0 から始まるインデックス、またはレコードを意味します。|  
|FFAsm.exe|送信パイプラインをエミュレートすることにより、フラット ファイル アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメント (複数可) をフラット ファイル ドキュメントにシリアル化またはアセンブルするようすを表示します。|  
|FFDasm.exe|受信パイプラインをエミュレートすることにより、フラット ファイル逆アセンブラー コンポーネントを直接呼び出して実行し、ユーザーのフラット ファイル ドキュメントを 1 つ以上の XML ドキュメントに解析または逆アセンブルするようすを表示します。|  
|Pipeline.exe|送信パイプラインまたは受信パイプラインを実行し、1 つ以上の入力ドキュメントとその部分、XSD スキーマ、および関連情報を受け取り、パイプラインの実行後に出力ドキュメントを生成します。 Pipeline.exe は BizTalk Server データベースにアクセスしないので、実行時に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースにアクセスする BizTalk Framework アセンブラー コンポーネントや逆アセンブラー コンポーネントが含まれるパイプラインは、サポートされません。|  
|XMLAsm.exe|送信パイプラインをエミュレートすることにより、XML アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメント (複数可) を 1 つの出力 XML ドキュメントにシリアル化、アセンブル、またはエンベロープするようすを表示します。|  
|XMLDasm.exe|受信パイプラインをエミュレートすることにより、XML 逆アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメントを 1 つ以上の XML ドキュメントに解析、逆アセンブル、またはエンベロープ解除するようすを表示します。|  
  
## <a name="usage"></a>使用方法  
 以下のセクションで、各ファイルについてさらに詳しく説明します。  
  
### <a name="dsdumpexe"></a>DSDump.exe  
 DSDump.exe を使用すると、ドキュメント スキーマ構造をダンプできます。この構造は、1 つ以上の XSD スキーマのメモリ内簡易表現で、フラット ファイルの注釈を含む場合と含まない場合があります。  
  
 DSDump.exe (ドキュメント スキーマ ダンプ ツール) は、次のコマンド ライン パラメーターをサポートしています。  
  
```  
DSDump.exe schemaFileName  
```  
  
 DSDump が成功すると、コンソールにドキュメント スキーマが出力されます。  
  
### <a name="ffasmexe"></a>FFAsm.exe  
 FFAsm.exe (フラット ファイル アセンブラー) は、次のコマンド ライン パラメーターをサポートしています。  
  
```  
usage: ffasm document... [-dm documentMask...]-bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -c ] [ -d ] [ -sb ] [ -m filenamemask ] [ -en encoding ] [ -v ]  
  
where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -c                 Display assembled FF message on the console  
  -d                 Demote properties  
  -sb                Set body schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Output message encoding name (e.g. windows-1252) or   
                         code page (e.g. 936)  
  -v                 Verbose mode  
  
file name macros:  
  %MessageID%        FF message identifier (Guid)  
  %MessagePartID%    FF message part identifier (Guid)  
  
```  
  
 たとえば、3 つの入力 XML ドキュメントを、ヘッダーを持つ 1 つのフラット ファイル ドキュメントにアセンブルし、プロパティを降格するには、次のコマンドを使用します。  
  
```  
FFAsm.exe file_in1.xml file_in2.xml file_in3.xml –hs myHeaderSchema.xsd –bs myBodySchema.xsd -d  
```  
  
### <a name="ffdasmexe"></a>FFDasm.exe  
 FFDasm.exe (フラット ファイル 逆アセンブラー) は、次のコマンド ライン パラメーターをサポートしています。  
  
```  
usage: ffdasm document -bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -s ] [ -c ] [ -p ] [ -m filenamemask ] [ -en encoding ] [ -v ]  
  
where:  
  document           Flat File document  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  encoding           Input message body part encoding name (e.g. windows-1252) or code page (e.g., 396)  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  
  
file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  
```  
  
 たとえば、ヘッダー、ボディ、およびトレーラーを持つフラット ファイル ドキュメントを逆アセンブルし、結果をコンソールに表示するには、次のコマンドを使用します。  
  
```  
FFDasm.exe file_in.txt –hs myHeaderSchema.xsd –bs myBodySchema.xsd –ts myTrailerSchema.xsd –c  
```  
  
### <a name="pipelineexe"></a>Pipeline.exe  
 Pipeline.exe (パイプライン ツール) は、次のコマンド ライン パラメーターをサポートしています。  
  
```  
usage: pipeline ( pipeline[.btp] | -pt pipelineTypeName [ -an assemblyName ] ) -d document... [ -part part... ] [ -s schema[.xsd][:namespace.type]... ] [ -proj project[.btproj] ] [ -p ] [ -c ] [ -t ] [ -m filenamemask ] [ -pm partfilenamemask ] [ -en encoding ] [ -v ]  
  
where:  
  pipeline                Pipeline file name  
  pipelineTypeName     Compiled pipeline assembly qualified type name (e.g.   
"MyPipelines.ReceivePipeline, MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66" or full name (e.g.   
"MyPipelines.ReceivePipeline") if assembly name is   
specified  
  assemblyName         Compiled pipeline assembly file name (e.g.   
MyPipelines.dll) or name (e.g. "MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66")  
  document             Input document(s)  
  part                 Input document's part  
  schema               Schema file name  
  namespace            Schema namespace (as in BizTalk project system)  
  type                 Schema type (as in BizTalk project system)  
  project              BizTalk project file  
  -p                   Display promoted context properties for receive and   
send pipelines, and promote context properties for   
send pipelines  
  -c                      Display output document on the console  
  -t                      Display elapsed time of components execution  
  filenamemask         Output message file name mask (default is   
Message_%MessageID%.out)  
  partfilenamemask     Output part file name mask (default is   
Part_%MessagePartID%.out)  
  encoding             Output message encoding name (e.g. windows-1252)   
or code page (e.g. 936)  
  -v                   Verbous mode  
  
note:  
You can specify namespace and type for schemas either using namespace.type notation in schema file reference or by using BizTalk project file.  
  
file name macros:  
  %MessageID%           Message identifier (Guid)  
  %MessagePartID%       Message part identifier (Guid)  
  %MessageNumber%       Message number  
  
```  
  
 たとえば、ファイル ReceivePipeline.btp (XML 逆アセンブラー コンポーネントと XML 検証コンポーネントが含まれる) から mySchema.xsd を使用して受信パイプラインを実行し、結果をコンソールに表示するには、次のコマンドを使用します。  
  
```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd:MyProject.MySchema -c  
  
```  
  
 \- または -  
  
```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd –proj MyProject.btproj -c  
  
```  
  
 最初の例では、修飾型名 (**MyProject.MySchema**)、スキーマは、コマンドライン引数として含まれています。 2 番目の例では、指定した BizTalk プロジェクト ファイルからスキーマが取得されます。  
  
 コンパイルされた [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクト ファイルからパイプラインを実行することもできます。次に例を示します (パイプラインはアセンブリ修飾型名によって参照されています)。  
  
```  
Pipeline.exe -pt "TestBtsProject.ReceivePipeline, TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  
  
 次の例では、型名とアセンブリ ファイル名でそれぞれ個別にパイプラインが参照されています。  
  
```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an TestBtsProject.dll -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c   
```  
  
 次の例では、アセンブリ名によってパイプラインが参照されています。  
  
```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an "TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  
  
 Pipeline.exe は、起動時に使用した資格情報で実行されます。 通常の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホスト インスタンスを実行するアカウントは使用されません。このため、データベース アクセスを必要とするコンポーネントが含まれているパイプラインは、実行できないことがあります。 Pipeline.exe を実行するアカウントに、必要な特権がすべて含まれていることを確認してください。  
  
 Pipeline.exe は、サード パーティのカスタム コンポーネントが含まれないカスタム パイプラインを確認するためにのみ使用してください。 サード パーティのカスタム コンポーネントが含まれたカスタム パイプラインを確認するために Pipeline.exe を使用しても、必要な出力は生成されます。 しかし、サード パーティのカスタム コンポーネントが含まれたカスタム パイプラインを展開した場合、受信ポートまたは送信ポートでこのパイプラインを使用し、その後 Pipeline.exe を使用してパイプラインにメッセージを送信すると、パイプラインは失敗し、BizTalk Server からエラーが返されます。  
  
### <a name="xmlasmexe"></a>XMLAsm.exe  
 XMLAsm.exe (XML アセンブラー ツール) は、次のコマンド ライン パラメーターをサポートしています。  
  
```  
usage: xmlasm document...[-dm documentmask...] -ds documentSchema... [ -es envelopeSchema... ] [ -c ] [ -d ] [ -sd ] [ -m filenamemask ] [ -v ]  
  
where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -c                 Display assembled XML message on the console  
  -d                 Demote properties  
  -sd                Set document schema(s) as design-time property  
  -d                 Demote properties  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  
  
file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  
```  
  
 たとえば、2 つの入力 XML ドキュメントを、エンベロープを持つ 1 つの XML ドキュメントにアセンブルし、結果をコンソールに表示するには、次のコマンドを使用します。  
  
```  
FFAsm.exe file_in1.xml file_in2.xml–es myEnvelopeSchema.xsd –ds myBodySchema.xsd –c  
```  
  
### <a name="xmldasmexe"></a>XMLDasm.exe  
 XMLDasm.exe は、次のコマンド ライン パラメーターをサポートしています。  
  
```  
usage: xmldasm document -ds documentSchema... [ -es envelopeSchema... ] [ -s ] [ -c ] [ -p ] [ -sd ] [ -se ] [ -m filenamemask ] [ -en encoding ] [ -v ]  
  
where:  
  document           XML document  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  -sd                Set document schema(s) as design-time property  
  -se                Set envelope schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Input message body part encoding name (e.g., windows-1252) or code page (e.g., 936)  
  -v                 Verbous mode  
  
file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  %MessageNumber%    XML message number  
  
```  
  
 たとえば、2 つのネストされたエンベロープを持つ XML ドキュメントを逆アセンブルし、結果をコンソールに表示するには、次のコマンドを使用します。  
  
```  
XmlDasm.exe file_in.txt –ds myDocumentSchema.xsd –es myEnvelopeSchema1.xsd –es myEnvelopeSchema2.xsd –c  
```  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)