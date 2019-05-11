---
title: FlatFileSend (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52dd0018-e272-40db-a26a-509d444d7106
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1389255ec1114b377e2e55d7dbaeaa7c1839163c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387855"
---
# <a name="flatfilesend-biztalk-server-sample"></a>FlatFileSend (BizTalk Server サンプル)
FlatFileSend サンプルは、使用する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]同等のフラット ファイルを XML ファイルに変換します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、受信場所として FFInput フォルダを構成します。 このフォルダーにサンプル ファイル FlatFileSend_in.xml など、ファイルを配置すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の手順を使用してこのファイルにメッセージを処理します。  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所フォルダ FFInput の入力ファイルからメッセージを読み取ります。  

2. XML を通じて、メッセージが渡された受信パイプライン。  

3. メッセージ ボックス データベースでは、メッセージがフラット ファイル アセンブラー コンポーネントで構成されている送信パイプラインに含まれるファイル送信ポートにルーティングされます。 フラット ファイル アセンブラー コンポーネントでは、XML メッセージをフラット ファイル スキーマを使用して、同等のフラット ファイル表現に変換します。  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 変換されたメッセージを送信アダプタ フォルダ FFOutput のテキスト ファイルに書き込みます。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 サンプル メッセージでは、このサンプルでは基本的な設計の多くによって決まります。 フラット ファイル アセンブラおよびカスタム送信パイプライン内のフラット ファイル スキーマを使用して、フラット ファイル メッセージをアセンブルする必要があります。 これらおよび他のデザイン要素は、次の表にまとめたものです。  


|    デザイン要素    |                                                                                                                                                                    選択理由                                                                                                                                                                    |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| カスタム送信パイプライン | -カスタム パイプラインはフラット ファイル アセンブラとフラット ファイル スキーマを使用して、インスタンス メッセージをフラット ファイル形式に変換するにはフラット ファイル アセンブラー自体はパイプラインし、で送信パイプラインを構成するときに使用することはできません、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 |
|   フラット ファイル スキーマ   |                                      -すべての定義、同じレコードとフィールドの特性 (構造体を含む) を XML スキーマとして、すべての XML インスタンス メッセージをフラット ファイル メッセージに (またはその逆) に変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供します。                                      |
| サブスクリプション フィルター  |                                                                                                          -サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。                                                                                                          |
|      [Xmlreceive]      |                                                                                                        -受信 XML メッセージの処理を実行します。 この例では、注文書の XML 表現は、送信元メッセージとして使用されます。                                                                                                        |

 これらの要素を結合して、受信場所から XML 形式で注文書メッセージを受け取るソリューションを作成し、フラット ファイルを書き込みますが、送信場所に注文します。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileSend  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                ファイル                |                                                                                           説明                                                                                            |
|---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              Cleanup.bat              | アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。 |
| FlatFileSend.btproj、FlatFileSend.sln |                                                                           このサンプルのプロジェクト ファイルとソリューション ファイルです。                                                                            |
|        FlatFileSendBinding.xml        |                                                                          ポートのバインドなど、自動化されたセットアップに使用されます。                                                                          |
|          FlatFileSend_in.xml          |                                                                                        サンプル入力ファイルです。                                                                                        |
|                PO.xsd                 |                                                                                  送信フラット ファイルのスキーマです。                                                                                  |
|           SendPipeline.btp            |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] フラット ファイル アセンブラ コンポーネントを含むパイプライン ファイルを送信します。                           |
|               Setup.bat               |                                                                            このサンプルをビルドおよび初期化するために使用されます。                                                                             |

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルを独自のフラット ファイル処理ソリューションの基礎として使用します。 多くの独自の要件に合わせて、このサンプルで使用されるデザイン要素を拡張することができます。  

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    *\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileSend  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - フォルダーには、入力 (ffinput フォルダ) とこのサンプルの出力 (FFOutput) フォルダを作成します。  

      *\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileSend  

   - コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

     > [!NOTE]
     >  このサンプルは、ポートを作成してバインドする際に、以下の警告を表示します。`Warning: Receive handler not specified for receive location "FlatFileSend_RL"; updating with first receive handler with matching transport type. Warning: Host not specified for orchestration "FlatFileSend"; updating with first available host.` これらの警告を無視してかまいません。 (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  

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

1.  ファイル FlatFileSend_in.xml のコピーを FFInput フォルダに配置します。  

2.  テキスト ファイルが FFOutput フォルダに作成されたことを確認します。 テキスト ファイルの名前は、メッセージ ID の GUID に基づきます。 このファイルには、XML 入力ファイル FlatFileSend_in.xml のフラット ファイルと同じが含まれています。  

## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 Setup.bat および Cleanup.bat の構成スクリプトは、次の管理用の Windows Management Instrumentation (WMI) スクリプトに依存します。  

- Start Send Port\StartSendPort.vbs  

- Enable Receive Location\EnableRecLoc  

- Remove Send Port\RemoveSendPort  

  セットアップとクリーンアップ バッチ ファイルは、次のような BTSTask を使用します。  

- **BTSTask ImportBindings**バインド ファイルを適用し、アプリケーション、ポート、およびバインドを作成するには  

- **BTSTask RemoveApp** FlatFileSendApplication を削除するには  

## <a name="see-also"></a>参照  
- [フラット ファイル スキーマ](../core/flat-file-schemas.md)   
- [既定のパイプライン](../core/default-pipelines.md)   
- [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
- **WMI スクリプトのサンプル** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)   
- [FlatFileReceive (BizTalk Server サンプル)](../core/flatfilereceive-biztalk-server-sample.md)
