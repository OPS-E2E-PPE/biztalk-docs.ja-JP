---
title: パイプライン ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5d9a2aeff4b73eebb95b8be8a76b92fb9c7848d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395761"
---
# <a name="pipeline-tools"></a>パイプライン ツール
Microsoft 付属のパイプライン ツール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソフトウェア開発キット (SDK) を使用すると、送信/受信ポートなど、BizTalk Server 環境を構成することがなく、パイプラインが正しく機能することを確認します。 パイプライン ツールを使用することもできます。  

-   Server 環境の外部のサード パーティのパイプライン コンポーネントをデバッグします。  

-   解析エンジンのエラー メッセージを診断します。  

-   コンパイル、展開、展開解除、および再コンパイルする負担が解消され、さまざまなスキーマを試してください。  

-   フラット ファイルと XML のアセンブラー/逆アセンブラーの動作について説明します。  

-   逆アセンブラーの出力を表示し、メッセージ コンテキスト プロパティが昇格され、その値を検出します。  

-   逆アセンブラーおよびアセンブラー コンポーネントなしの送信/受信パイプラインを実行する (たとえば、S/MIME デコーダーの出力を表示できます)。  

-   (メッセージング サブシステム全体) ではなくだけで、パイプラインの詳細なパフォーマンスの測定値を確認します。  

## <a name="location-in-sdk"></a>SDK でのパス  
 \<*Installation Path*\>\SDK\Utilities\PipelineTools  

 実行、デバッグ、およびパイプライン、プロファイリングのパイプライン ツールを使用してパイプライン コンポーネント (つまり、フラット ファイル、XML アセンブラ/逆アセンブラ コンポーネント)。  

## <a name="file-inventory"></a>ファイルのインベントリ  
 次の表では、パイプライン ツール ファイルの一覧し、その目的について説明します。  


|   ファイル    |                                                                                                                                                                                                                                説明                                                                                                                                                                                                                                 |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  DSDump.exe  |                                                ドキュメント スキーマ構造をダンプするために使用します。この構造は、1 つ以上の XSD スキーマのメモリ内簡易表現で、フラット ファイルの注釈を含む場合と含まない場合があります。 $Root$0$3$2 などの解析エンジン エラーが発生し、デコードする必要がある場合に、このツールが役立ちます。 $ 後の数値は、ドキュメント スキーマに表示される、0 から始まるインデックスまたはレコードを意味します。                                                |
|  FFAsm.exe   |                                                                                                                                     送信パイプラインをエミュレートすることにより、フラット ファイル アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメント (複数可) をフラット ファイル ドキュメントにシリアル化またはアセンブルするようすを表示します。                                                                                                                                      |
|  FFDasm.exe  |                                                                                                                               受信パイプラインをエミュレートすることにより、フラット ファイル逆アセンブラー コンポーネントを直接呼び出して実行し、ユーザーのフラット ファイル ドキュメントを 1 つ以上の XML ドキュメントに解析または逆アセンブルするようすを表示します。                                                                                                                               |
| Pipeline.exe | 実行を送信または受信パイプラインです。1 つまたは複数の入力ドキュメントと部分、XSD スキーマと関連情報を受け取ります生成、パイプラインの後の出力ドキュメントを実行します。 Pipeline.exe は BizTalk Framework アセンブラーおよび逆アセンブラー コンポーネントを含むパイプラインにアクセスするために BizTalk Server のデータベースをアクセスしない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行中にデータベースがサポートされていません。 |
|  XMLAsm.exe  |                                                                                                                                 送信パイプラインをエミュレートすることにより、XML アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメント (複数可) を 1 つの出力 XML ドキュメントにシリアル化、アセンブル、またはエンベロープするようすを表示します。                                                                                                                                  |
| XMLDasm.exe  |                                                                                                                             受信パイプラインをエミュレートすることにより、XML 逆アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメントを 1 つ以上の XML ドキュメントに解析、逆アセンブル、またはエンベロープ解除するようすを表示します。                                                                                                                              |

## <a name="usage"></a>使用方法  
 各ファイルの詳細については、次のセクションで提供されます。  

### <a name="dsdumpexe"></a>DSDump.exe  
 DSDump.exe を使用すると、フラット ファイルの注釈の有無など、1 つまたは複数の XSD スキーマのメモリ内簡易表現には、ドキュメント スキーマ構造をダンプできます。  

 DSDump.exe (ドキュメント スキーマ ダンプ ツール) は、次のコマンド ライン パラメーターをサポートしています。  

```  
DSDump.exe schemaFileName  
```  

 DSDump を成功するが発生した場合に、コンソールにドキュメント スキーマを出力します。  

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

 たとえば、ヘッダーとプロパティの降格を単一のフラット ファイル ドキュメントに 3 つの入力 XML ドキュメントをアセンブルする場合は、次のコマンドを使用します。  

```  
FFAsm.exe file_in1.xml file_in2.xml file_in3.xml –hs myHeaderSchema.xsd –bs myBodySchema.xsd -d  
```  

### <a name="ffdasmexe"></a>FFDasm.exe  
 FFDasm.exe (フラット ファイル逆アセンブラー) は、次のコマンド ライン パラメーターをサポートしています。  

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

 たとえば、ヘッダー、本文、およびトレーラーのあるフラット ファイル ドキュメントを逆アセンブルし、結果をコンソールに表示する場合は、次のコマンドを使用します。  

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

 たとえば、ファイル ReceivePipeline.btp (XML 逆アセンブラーおよび XML 検証ツール コンポーネントがある) から受信パイプラインを実行する mySchema.xsd と表示を使用して、コンソールに結果は次のコマンドを使用します。  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd:MyProject.MySchema -c  

```  

 \- または -  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd –proj MyProject.btproj -c  

```  

 最初の例では、修飾型名 (**MyProject.MySchema**)、スキーマは、コマンドラインの引数として含まれています。 2 番目の例では、スキーマが指定した BizTalk プロジェクト ファイルから取得されます。  

 コンパイルされたからパイプラインを実行することもできます。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト (パイプラインはアセンブリ修飾型名で参照されている) 次の例のように、ファイル。  

```  
Pipeline.exe -pt "TestBtsProject.ReceivePipeline, TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 次の例では、パイプラインは、型名とアセンブリ ファイル名によって個別に参照されます。  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an TestBtsProject.dll -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c   
```  

 次の例は、アセンブリ名によって参照されているパイプラインを示します。  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an "TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 Pipeline.exe は、起動時に使用した資格情報では実行されます。 通常のアカウントが使用しない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースへのアクセスを必要とするコンポーネントを含むパイプラインを実行することができないため、ホスト インスタンスを実行します。 必要なすべての特権を持つアカウントで Pipeline.exe を実行することを確認します。  

 Pipeline.exe を使用して、サード パーティ製のカスタム コンポーネントなしのカスタム パイプラインを確認する必要がありますのみです。 Pipeline.exe を使用してサード パーティのカスタム コンポーネントを使用するカスタム パイプラインを確認する場合、Pipeline.exe は、目的の出力を生成します。 ただし、展開する場合のサード パーティ カスタム コンポーネントでは、同じカスタム パイプラインで受信パイプラインを使用して、または送信ポート、および Pipeline.exe を使用して、パイプラインにメッセージを送信、パイプラインは失敗し、BizTalk Server はエラーを返します。  

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

 など、エンベロープを持つ 1 つの XML ドキュメントに 2 つの入力 XML ドキュメントをアセンブルし、結果をコンソールに表示する場合は、次のコマンドを使用します。  

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

 たとえば、2 つのネストされたエンベロープを持つ XML ドキュメントを逆アセンブルし、結果をコンソールに表示する場合は、次のコマンドを使用します。  

```  
XmlDasm.exe file_in.txt –ds myDocumentSchema.xsd –es myEnvelopeSchema1.xsd –es myEnvelopeSchema2.xsd –c  
```  

## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)