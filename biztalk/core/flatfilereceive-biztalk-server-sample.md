---
title: FlatFileReceive (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bd9e8d-6ed9-49c4-8437-c0c8b2a9a78d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae4cdace5a38d3b6a7058f16e894ca9bdbe912c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975539"
---
# <a name="flatfilereceive-biztalk-server-sample"></a>FlatFileReceive (BizTalk Server サンプル)
FlatFileReceive サンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してフラット ファイルを同等の .xml ファイルに変換する方法を示します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、FFInput フォルダを受信場所として構成します。 このフォルダーにサンプル ファイル FlatFileReceive_in.txt のようなファイルを置くと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はこのファイル内のメッセージを次の手順で処理します。  

1.  受信場所フォルダ FFInput の入力ファイルからメッセージを読み取ります。  

2.  受信パイプラインにおいて、フラット ファイル逆アセンブラ コンポーネントが、メッセージをフラット ファイル形式から同等の XML メッセージに変換します。  

3.  MessageBox データベース内で、メッセージが FILE 送信ポートに回送されます。この送信ポートは、XML メッセージを送信アダプタ フォルダ FFOutput 内のファイルに書き込みます。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 サンプル メッセージはこのサンプル内の基本デザインの多くを示しています。 フラット ファイル メッセージは、フラット ファイル逆アセンブラおよびカスタム受信パイプライン内のフラット ファイル スキーマを使用して逆アセンブルする必要があります。 これらのデザイン要素と他のデザイン要素を次の表にまとめます。  


|     デザイン要素      |                                                                                                                                                                  選択理由                                                                                                                                                                   |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| カスタム受信パイプライン | -カスタム パイプラインはフラット ファイル逆アセンブラーを使用し、変換、受信するフラット ファイル スキーマは、注文メッセージを購入します。 フラット ファイル逆アセンブラー自体はパイプラインではなく、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでの受信パイプラインの構成時に使用することはできません。 |
|    フラット ファイル スキーマ     |                           -すべての定義、同じレコードとフィールドの特性 (構造体を含む) を XML スキーマとして、すべてのフラット ファイル インスタンス メッセージを同等の XML インスタンスに変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供メッセージ (またはその逆)。                           |
|   サブスクリプション フィルター   |                                                                                                        -サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。                                                                                                         |
|       XMLTransmit       |                                                                                                           -出力方向の基本的なアセンブリを実行する XML メッセージを必要な箇所です。 PassThruTransmit パイプラインでは追加のサポートは行われません。                                                                                                            |

 これらの要素が組み合わされて、フラット ファイル形式の注文書メッセージを受信場所から受け入れ、変換した XML 表現を送信場所に書き込むソリューションが作成されます。  

 このサンプルの設計には次の考慮事項が適用されます。  

-   フラット ファイル スキーマ (PO.xsd) には、注文書フラット ファイルの構造を記述した拡張注釈が含まれています。 これらのファイルは手動で作成できますが、その多くはフラット ファイル ウィザードを使用して生成できます。  

-   フラット ファイル スキーマは Unqualified の elementFormDefault 値を使用します。 これにより正しい結果がもたらされますが、結果には予期しない XML 名前空間 (xmlns) 修飾が追加されます。 この問題を避けるには、Qualified の elementFormDefault を使用してください。  

-   XmlTransmit が送信パイプラインとして使用されます。 プロパティの降格または他のメッセージ処理が送信ポートで必要ない場合は、PassThruTransmit パイプラインを使用してください。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                   ファイル                   |                                                                                           説明                                                                                            |
|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                 Cleanup.bat                 | アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。 |
|            FFReceivePipeline.btp            |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、フラット ファイル逆アセンブラー コンポーネントを含むパイプライン ファイルを受信します。                        |
| FlatFileReceive.btproj, FlatFileReceive.sln |                                                                           このサンプルのプロジェクト ファイルとソリューション ファイルです。                                                                            |
|           FlatFileReceive_in.txt            |                                                                                        サンプル入力ファイルです。                                                                                        |
|         FlatFileReceiveBinding.xml          |                                                                          ポートのバインドなど、自動化されたセットアップに使用されます。                                                                          |
|                   PO.xsd                    |                                                                                受信フラット ファイルのスキーマです。                                                                                 |
|                  Setup.bat                  |                                                                            このサンプルをビルドおよび初期化するために使用されます。                                                                             |

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルは、独自のフラット ファイル処理ソリューションの基礎として使用してください。 このサンプルで使用されているデザイン要素の多くは、独自の要件に合うように拡張できます。  

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - 次のフォルダに、このサンプルの入力 (FFInput) フォルダと出力 (FFOutput) フォルダを作成します。  

      *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive  

   - このサンプル用に Visual Studio プロジェクトをコンパイルおよび展開します。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

     > [!NOTE]
     >  このサンプルには、作成してポートをバインドする場合は、次の警告が表示されます:`Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.`これらの警告を無視してかまいません。 (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  

   - 受信場所を有効にし、送信ポートを開始します。  

> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
> 
> [!NOTE]
>  開き、Setup.bat を実行することがなく、このサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。  
> 
> [!NOTE]
>  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

## <a name="running-this-sample"></a>このサンプルの実行  

1.  ファイル FlatFileReceive_in.txt を FFInput フォルダにコピーします。  

2.  .xml ファイルが FFOutput フォルダに作成されることを確認します。 出力ファイルの名前はメッセージ ID GUID に基づきます。 このファイルには、受信フォルダに配置されたフラット ファイルに相当する XML が含まれています。  

## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 Setup.bat および Cleanup.bat の 2 つの構成スクリプトは、次の管理用 Windows Management Instrumentation (WMI) スクリプトに依存しています。  

- Start Send Port\StartSendPort.vbs  

- Enable Receive Location\EnableRecLoc  

- Remove Send Port\RemoveSendPort  

  セットアップおよびクリーンアップのバッチ ファイルでは、次のように BTSTask を使用します。  

- **BTSTask ImportBindings**バインド ファイルを適用し、アプリケーション、ポート、およびバインドを作成するには  

- **BTSTask RemoveApp** FlatFileReceiveApplication を削除するには  

## <a name="see-also"></a>参照  
- [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
- [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
- [フラット ファイル スキーマ](../core/flat-file-schemas.md)   
- [既定のパイプライン](../core/default-pipelines.md)   
- **WMI スクリプトのサンプル** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
- [FlatFileSend (BizTalk Server サンプル)](../core/flatfilesend-biztalk-server-sample.md)
