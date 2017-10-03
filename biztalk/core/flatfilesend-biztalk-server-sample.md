---
title: "FlatFileSend (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52dd0018-e272-40db-a26a-509d444d7106
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bdbc0d4e06e5d6980ec984c8c701f4ee7ded7ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="flatfilesend-biztalk-server-sample"></a>FlatFileSend (BizTalk Server サンプル)
FlatFileSend サンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、XML ファイルを同等のフラット ファイルに変換する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、FFInput フォルダを受信場所として構成します。 このフォルダーにサンプル ファイル FlatFileSend_in.xml のようなファイルを置くと、このファイル内のメッセージが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって、次の手順で処理されます。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、受信場所フォルダー FFInput の入力ファイルからメッセージを読み取ります。  
  
2.  メッセージが XML 受信パイプライン経由で受け渡されます。  
  
3.  MessageBox データベースで、メッセージが FILE 送信ポートにルーティングされます。このポートには、フラット ファイル アセンブラ コンポーネントを使用するよう構成された送信パイプラインがあります。 フラット ファイル アセンブラ コンポーネントは、フラット ファイル スキーマを使用して、XML メッセージを同等のフラット ファイル表現に変換します。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が、変換されたメッセージを送信アダプター フォルダー FFOutput のテキスト ファイルに書き込みます。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 サンプル メッセージはこのサンプル内の基本デザインの多くを示しています。 フラット ファイル メッセージは、カスタム送信パイプライン内のフラット ファイル アセンブラとフラット ファイル スキーマを使用してアセンブルする必要があります。 これらのデザイン要素と他のデザイン要素を次の表にまとめます。  
  
|デザイン要素|選択理由|  
|--------------------|--------------------------|  
|カスタム送信パイプライン|-カスタム パイプラインはフラット ファイル アセンブラとフラット ファイル スキーマを使用して、インスタンス メッセージをフラット ファイル形式に変換するにはフラット ファイル アセンブラー自体はパイプラインで送信パイプラインを構成するときに使用することはできません、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。|  
|フラット ファイル スキーマ|-すべて、同じレコードおよびフィールドの特性 (構造を含む) として定義 XML スキーマとすべての XML インスタンス メッセージをフラット ファイル メッセージに (またはその逆) に変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供します。|  
|サブスクリプション フィルター|-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャして実際のルーティングを実行します。|  
|XMLReceive|-受信 XML メッセージの処理を実行します。 この例では、注文書の XML 表現が変換対象のメッセージとして使用されます。|  
  
 これらの要素が組み合わされて、XML 形式の注文書メッセージを受信場所から受け入れ、フラット ファイル形式の注文書を送信場所に書き込むソリューションが作成されます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<サンプル パス >*\Pipelines\AssemblerDisassembler\FlatFileSend  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Cleanup.bat|アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|FlatFileSend.btproj、FlatFileSend.sln|このサンプルのプロジェクト ファイルとソリューション ファイルです。|  
|FlatFileSendBinding.xml|ポートのバインドなど、自動化されたセットアップに使用されます。|  
|FlatFileSend_in.xml|サンプル入力ファイルです。|  
|PO.xsd|送信フラット ファイルのスキーマです。|  
|SendPipeline.btp|フラット ファイル アセンブラー コンポーネントを含む [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信パイプライン ファイルです。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルは、独自のフラット ファイル処理ソリューションの基礎として使用してください。 このサンプルで使用されているデザイン要素の多くは、独自の要件に合うように拡張できます。  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     *\<サンプル パス >*\Pipelines\AssemblerDisassembler\FlatFileSend  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   次のフォルダに、このサンプルの入力 (FFInput) フォルダと出力 (FFOutput) フォルダを作成します。  
  
         *\<サンプル パス >*\Pipelines\AssemblerDisassembler\FlatFileSend  
  
    -   コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
        > [!NOTE]
        >  このサンプルを作成して、ポートのバインド時に、次の警告が表示されます:`Warning: Receive handler not specified for receive location "FlatFileSend_RL"; updating with first receive handler with matching transport type. Warning: Host not specified for orchestration "FlatFileSend"; updating with first available host.`これらの警告を無視してかまいません。 (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  
  
    -   受信場所を有効にし、送信ポートを開始します。  
  
> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
> [!NOTE]
>  開き、Setup.bat を実行しなくてもこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。  
  
> [!NOTE]
>  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
1.  ファイル FlatFileSend_in.xml を FFInput フォルダにコピーします。  
  
2.  テキスト ファイルが FFOutput フォルダに作成されることを確認します。 テキスト ファイルの名前は、メッセージ ID の GUID に基づきます。 このファイルには、XML 入力ファイル FlatFileSend_in.xml と同等のフラット ファイルが含まれています。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 Setup.bat および Cleanup.bat の 2 つの構成スクリプトは、次の管理用 Windows Management Instrumentation (WMI) スクリプトに依存しています。  
  
-   Start Send Port\StartSendPort.vbs  
  
-   Enable Receive Location\EnableRecLoc  
  
-   Remove Send Port\RemoveSendPort  
  
 セットアップおよびクリーンアップのバッチ ファイルでは、次のように BTSTask を使用します。  
  
-   **BTSTask ImportBindings**バインド ファイルを適用し、アプリケーション、ポート、およびバインドを作成するには  
  
-   **BTSTask RemoveApp** FlatFileSendApplication を削除するには  
  
## <a name="see-also"></a>参照  
-  [フラット ファイル スキーマ](../core/flat-file-schemas.md)   
-  [既定のパイプライン](../core/default-pipelines.md)   
-  [パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
-  **WMI スクリプト サンプル**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
-  [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
-  [FlatFileReceive (BizTalk Server サンプル)](../core/flatfilereceive-biztalk-server-sample.md)