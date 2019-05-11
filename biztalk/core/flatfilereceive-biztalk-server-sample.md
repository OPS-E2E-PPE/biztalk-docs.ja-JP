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
ms.openlocfilehash: 6fcae5883f5230b7cd0e97051707133626c87cb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388055"
---
# <a name="flatfilereceive-biztalk-server-sample"></a>FlatFileReceive (BizTalk Server サンプル)
FlatFileReceive サンプルを使用する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]同等の .xml ファイルをフラット ファイルに変換します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、受信場所として FFInput フォルダを構成します。 このフォルダーにサンプル ファイル FlatFileReceive_in.txt をなど、ファイルを配置すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の一連の手順を使用してこのファイルにメッセージを処理します。  

1.  受信場所フォルダ FFInput の入力ファイルからメッセージを読み取ります。  

2.  受信パイプラインでは、フラット ファイル逆アセンブラー コンポーネントは、フラット ファイル形式から同等の XML メッセージにメッセージを変換します。  

3.  メッセージ ボックス データベースでは、メッセージは XML メッセージを送信アダプタ フォルダ FFOutput 内のファイルに書き込むファイルの送信ポートにルーティングされます。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 サンプル メッセージでは、このサンプルでは基本的な設計の多くによって決まります。 フラット ファイル メッセージは、フラット ファイル逆アセンブラおよびカスタム受信パイプライン内のフラット ファイル スキーマを使用して逆アセンブルする必要があります。 これらおよび他のデザイン要素は、次の表にまとめたものです。  


|     デザイン要素      |                                                                                                                                                                  選択理由                                                                                                                                                                   |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| カスタム受信パイプライン | -カスタム パイプラインはフラット ファイル逆アセンブラーを使用し、変換、受信するフラット ファイル スキーマは、注文メッセージを購入します。 フラット ファイル逆アセンブラー自体はパイプラインし、での受信パイプラインを構成するときに使用できません、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 |
|    フラット ファイル スキーマ     |                           -すべての定義、同じレコードとフィールドの特性 (構造体を含む) を XML スキーマとして、すべてのフラット ファイル インスタンス メッセージを同等の XML インスタンスに変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供メッセージ (またはその逆)。                           |
|   サブスクリプション フィルター   |                                                                                                        -サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。                                                                                                         |
|       XMLTransmit       |                                                                                                           -出力方向の基本的なアセンブリを実行する XML メッセージを必要な箇所です。 PassThruTransmit パイプラインでは追加のサポートは行われません。                                                                                                            |

 これらの要素は、受信場所からフラット ファイル形式で注文書メッセージを受け取り、送信場所に結果の XML 表現を書き込みますソリューションを生成するために結合されます。  

 このサンプルのデザインに次の考慮事項が適用されます。  

-   フラット ファイル スキーマ (PO.xsd) には、注文書フラット ファイルの構造を記述した拡張注釈が含まれています。 これらのファイルを手動で作成できますが、多くは、フラット ファイル ウィザードを使用して生成できます。  

-   フラット ファイル スキーマは、Unqualified の elementFormDefault 値を使用します。 正しい結果が生成されますが、追加し、予期しない XML 名前空間 (xmlns) の制限があります。 この問題を回避するために、Qualified の elementFormDefault を使用します。  

-   [Xmltransmit] は、送信パイプラインとして使用されます。 送信ポートのプロパティの降格または他のメッセージ処理が不要な場合は、PassThruTransmit パイプラインを使用します。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                   ファイル                   |                                                                                           説明                                                                                            |
|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                 Cleanup.bat                 | アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。 |
|            FFReceivePipeline.btp            |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] フラット ファイル逆アセンブラー コンポーネントを含むパイプライン ファイルを受信します。                        |
| FlatFileReceive.btproj、FlatFileReceive.sln |                                                                           このサンプルのプロジェクト ファイルとソリューション ファイルです。                                                                            |
|           FlatFileReceive_in.txt            |                                                                                        サンプル入力ファイルです。                                                                                        |
|         FlatFileReceiveBinding.xml          |                                                                          ポートのバインドなど、自動化されたセットアップに使用されます。                                                                          |
|                   PO.xsd                    |                                                                                受信フラット ファイルのスキーマです。                                                                                 |
|                  Setup.bat                  |                                                                            このサンプルをビルドおよび初期化するために使用されます。                                                                             |

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルを独自のフラット ファイル処理ソリューションの基礎として使用します。 多くの独自の要件に合わせて、このサンプルで使用されるデザイン要素を拡張することができます。  

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - フォルダーには、入力 (ffinput フォルダ) とこのサンプルの出力 (FFOutput) フォルダを作成します。  

      *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive  

   - コンパイルし、このサンプルの Visual Studio プロジェクトを展開します。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

     > [!NOTE]
     >  このサンプルでは、作成してポートをバインドする場合は、次の警告が表示されます。`Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.` これらの警告を無視してかまいません。 (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  

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

1.  ファイル FlatFileReceive_in.txt のコピーを FFInput フォルダに配置します。  

2.  .Xml ファイルが FFOutput フォルダに作成されたことを確認します。 出力ファイルの名前は、メッセージ ID の GUID に基づきます。 このファイルには、受信フォルダーに配置されたフラット ファイルに相当する XML が含まれています。  

## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 Setup.bat および Cleanup.bat の構成スクリプトは、次の管理用の Windows Management Instrumentation (WMI) スクリプトに依存します。  

- Start Send Port\StartSendPort.vbs  

- Enable Receive Location\EnableRecLoc  

- Remove Send Port\RemoveSendPort  

  セットアップとクリーンアップ バッチ ファイルは、次のような BTSTask を使用します。  

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
