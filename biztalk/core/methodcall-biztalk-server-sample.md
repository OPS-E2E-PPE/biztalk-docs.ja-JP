---
title: MethodCall (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, calling
- examples, orchestrations
- orchestrations, methods
ms.assetid: 6bdc72da-9478-403a-b706-3089b7374ac7
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78e190920695ebfb1f5654dcb4abcf95beab085f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394498"
---
# <a name="methodcall-biztalk-server-sample"></a>MethodCall (BizTalk Server サンプル)
MethodCall サンプルを呼び出す方法を示します、します。BizTalk Server オーケストレーションからの NET ベースのメソッド。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルのやり取りをします。次の一連の手順を使用して、NET ベースのメソッド:  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーションは、In フォルダから XML 入力ファイルを取得します。 このファイルの追加に関する情報を格納する、または減算を実行する数値演算ライブラリをします。  

2. オーケストレーションでは、加算または減算を XML 入力ファイルで指定された実行に含まれる数値演算ライブラリを呼び出します。  

3. 数値演算ライブラリのメソッドを適切な**追加**または**減算**要求された計算を行い、結果を XML ドキュメントとしてパッケージ化します。  

4. オーケストレーションは、生成された .xml ファイルを Out フォルダに配置します。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルでは、次の機能を使用します。  

-   オーケストレーションで昇格させたプロパティを活用できます。 InputSchema.xsd の 3 つの要素は、識別フィールドとして昇格されます。 オーケストレーションでは、入力メッセージを受信したときにこれら 3 つのフィールドの値を取得し、オーケストレーションで宣言された対応する変数に割り当てます。  

-   使用して、**判断**図形をオーケストレーションに"if then else"ロジックを表現します。 入力した後、オーケストレーションは、識別フィールドの値を内部変数に割り当てる、**判断**図形を加算または減算を実行するかどうかを確認します。 実行する操作が必要がない場合、オーケストレーションは終了します。  

-   オーケストレーションから外部アセンブリを呼び出します。 オーケストレーションが外部を呼び出し、加算が実行する場合は、C#加算を実行するには、アセンブリと 2 つのパラメーターに渡されます。 減算に同じ手順が適用されます。  

    > [!NOTE]
    >  オーケストレーション; からを呼び出すには、グローバル アセンブリ キャッシュにアセンブリをインストールする必要があります。それ以外の場合、XLANG エラーが実行時に表示されます。  

-   使用して、**メッセージの割り当て**図形を出力メッセージを構築します。  

-   式図形で次のコードを配置することで、オーケストレーションをデバッグします。  

    ```  
    System.Diagnostics.Debug.WriteLine(iResult);  
    ```  

     使用して、イベント ログに、結果を記述することもできます。  

    ```  
    System.Diagnostics.EventLog.WriteEntry("MethodCall SDK Sample Debug", System.String.Format("Result = {0}", iResult);  
    ```  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Orchestrations\MethodCall\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                                          ファイル                                           |                                                                                           説明                                                                                            |
|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        Cleanup.bat                                         | アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。 |
|                                         Input.xml                                          |                                                                                        サンプル入力ファイルです。                                                                                        |
|                                         Setup.bat                                          |                                                                            このサンプルをビルドおよび初期化するために使用されます。                                                                             |
| \MathLibrary フォルダー。<br /><br /> AssemblyInfo.cs, MathHelper.cs, MathLibrary.csproj |                                                                このサンプルで使用される数値演算ライブラリのプロジェクトおよびソース ファイル。                                                                |
|       \MethodCallSample フォルダー。<br /><br /> InputSchema.xsd、OutputSchema.xsd       |                                                                    入力と出力 .xml のスキーマ ファイルをそれぞれします。                                                                    |
| \MethodCallSample フォルダー。<br /><br /> MethodCallSample.btproj、MethodCallSample.sln |                                                                           このサンプルのプロジェクト ファイルとソリューション ファイルです。                                                                            |
|          \MethodCallSample フォルダー。<br /><br /> MethodCallSampleBinding.xml          |                                                                          ポートのバインドなど、自動化されたセットアップに使用されます。                                                                          |
|             \MethodCallSample フォルダー。<br /><br /> MethodCallService.odx             |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 要求された計算を実行する数値演算ライブラリを呼び出すオーケストレーションです。                |

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

#### <a name="to-build-and-initialize-the-methodcall-sample"></a>ビルドして初期化 MethodCall サンプル  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    \<*パスのサンプル*\>\Orchestrations\MethodCall  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - 入力 (In) フォルダと出力 (Out) フォルダ MethodCall フォルダに、このサンプルを作成します。  

   - このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、生成されたアセンブリを展開します。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所と、オーケストレーションの送信ポートおよび受信ポートを作成しバインドします。  

   - 受信場所を有効にし、送信ポートを開始します。 オーケストレーションを参加させ、開始します。  

> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  

## <a name="running-this-sample"></a>このサンプルの実行  

#### <a name="to-run-the-methodcall-sample"></a>MethodCall サンプルを実行するには  

1.  Input.xml ファイルのコピーを In フォルダに貼り付けます。  

2.  .Xml ファイルが Out フォルダに作成されたことを確認します。 このファイルには、要求された加算または減算の計算の結果が含まれています。 このファイルの名前の形式が\< *MessageID*\>、.xml、 *\<MessageID\>* メッセージを一意に識別するために生成される GUID.  

3.  別の加算または減算を要求する入力ファイルを変更することができます。  

## <a name="uninstalling-this-sample"></a>このサンプルのアンインストール  

#### <a name="to-uninstall-the-methodcall-sample"></a>MethodCall サンプルをアンインストールするには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) に\<*サンプル パス*\>\Orchestrations\MethodCall\\します。  

2. Cleanup.bat を実行します。  

## <a name="see-also"></a>参照  
 [オーケストレーション (BizTalk Server サンプル フォルダー)](../core/orchestrations-biztalk-server-samples-folder.md)