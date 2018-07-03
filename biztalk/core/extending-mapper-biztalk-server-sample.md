---
title: Extending Mapper (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Mapper, examples
- XML tools
- BizTalk Mapper, extending
- examples, BizTalk Mapper
- examples, XML tools
ms.assetid: 6010a13f-b715-4766-ad91-5aa9b98589e3
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff0cf33f00688b5b609123a644a5d2a298ecaf01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995811"
---
# <a name="extending-mapper-biztalk-server-sample"></a>Extending Mapper (BizTalk Server サンプル)
Extending Mapper サンプルは、BizTalk マッパーの使用方法および拡張方法を示します。 このサンプルには、複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マップ ファイル (.btm) が含まれており、それぞれが BizTalk マッパーの異なる特徴を示しています。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 Extending Mapper サンプルは、コンテンツ ベースのルーティング (CBR) を使用し、オーケストレーションは使用しません。 サンプル送信ポートに対してフィルターを指定すると、サンプル送信ポートがサンプル受信ポートに直接接続されます。 送信ポートに対してマップが指定され、その送信ポートが処理済みのドキュメントに適用されます。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \XmlTools\ExtendingMapper  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                                                                             ファイル                                                                             |                                                         説明                                                          |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| MapperClassLibrary\AssemblyInfo.cs、MapperClassLibrary\MapperClassLibrary.csproj、MapperClassLibrary\MapperHelper.cs、MapperClassLibrary\MapperClassLibrary.sln | Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]® プロジェクト ファイルおよび Visual C#® ソース ファイルです。 |
|                                                                           Cleanup.bat                                                                           |                      アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。                       |
|                                                                         Destination.xsd                                                                         |                                                         スキーマ ファイルです。                                                         |
|                                                           ExtendingMapper.btproj、ExtendingMapper.sln                                                           |                                     このサンプルの BizTalk プロジェクト ファイルとソリューション ファイルです。                                      |
|                                                                       ExtendingMapper.xml                                                                       |                                                         ソース XML です。                                                          |
|                                                                   ExtendingMapperBinding.xml                                                                    |                                                         バインド XML です。                                                         |
|                                                                      ExternalAssembly.xml                                                                       |                                                    外部アセンブリ XML です。                                                    |
|                                                                      OverridingMapXslt.btm                                                                      |                                                          マップ ファイル。                                                           |
|                                                                      OverridingMapXslt.xml                                                                      |                                                     マップ XML をオーバーライドします。                                                      |
|                                                                     OverridingMapXslt.xslt                                                                      |                                                 マップ スタイルシートをオーバーライドします。                                                  |
|                                                                Scriptor_CallExternalAssembly.btm                                                                |                                                       サンプル マップ ファイルです。                                                       |
|                                                            Scriptor_GlobalVariableInInlineScript.btm                                                            |                                                       サンプル マップ ファイルです。                                                       |
|                                                                   Scriptor_InlineScripts.btm                                                                    |                                                       サンプル マップ ファイルです。                                                       |
|                                                                     Scriptor_InlineXslt.btm                                                                     |                                                       サンプル マップ ファイルです。                                                       |
|                                                         Scriptor_InlineXsltCallingExternalAssembly.btm                                                          |                                                       サンプル マップ ファイルです。                                                       |
|                                                                  Scriptor_XsltCalltemplate.btm                                                                  |                                                       サンプル マップ ファイルです。                                                       |
|                                                                            Setup.bat                                                                            |                                           サンプルをビルドおよび初期化するために使用されます。                                           |
|                                                                           Source.xsd                                                                            |                                                         スキーマ ファイルです。                                                         |

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順を使用して、Extending Mapper サンプルをビルドおよび初期化します。  

#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  

1. コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。  

    *\<パスのサンプル\>* \XmlTools\ExtendingMapper  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - このサンプルで使用される入力 (\In) フォルダーと出力 (\Out) フォルダーを作成します。  

   - コンパイルし、展開、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

     Scriptor_CallExternalAssembly.btm マップまたは Scriptor_InlineXsltCallingExternalAssembly.btm マップを使用する場合は、Visual Studio で ExtendingMapper.sln を開き、次の変更を行います (それ以外の場合は、手順 3. に進みます)。  

   1. ソリューション エクスプローラーで、Scriptor_CallExternalAssembly.btm を開きます。  

   2. マッパー グリッドで、スクリプト Functoid を選択します。  

   3. プロパティ グリッドで、選択、**スクリプト**プロパティ functoid スクリプトを構成する場合、省略記号 (...) ボタンをクリックします。  

   4. **スクリプト Functoid の構成**ダイアログ ボックスで、**スクリプト Functoid の構成**、して、次を指定します。  


      |      設定対象       |                           次の値に設定                            |
      |---------------------|--------------------------------------------------------------|
      |   **スクリプトの種類**   |                      外部アセンブリ                       |
      | **スクリプト アセンブリ** | Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary |
      |  **スクリプト クラス**   |    Microsoft.Samples.BizTalk.ExtendingMapper.MapperHelper    |
      |  **スクリプト メソッド**  |                           MyConcat                           |


   5. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**ファイル**] メニューの [選択**保存**をマップ ファイルへの変更を保存し、ソリューションを閉じます。  

3. 任意のキーを押して Setup.bat を続行します。  

   > [!IMPORTANT]
   >  Scriptor_InlineXsltCallingExternalAssembly.btm を使用する場合、ExternalAssembly.xml ファイルを編集する必要があります。 BizTalk は ExternalAssembly.xml を使用して、マッパー拡張オブジェクトの登録済み名前空間を .NET アセンブリにマップします。 依存アセンブリはその完全修飾名 (自動的に生成される公開キー トークンを含む) で参照されるため、この値を更新する必要があります。 Scriptor_InlineXsltCallingExternalAssembly.btm を使用しない場合は、手順 a. ～ e. を実行する必要はありません。  

4. Windows エクスプ ローラーに移動します。 \<Windows フォルダー\>\assembly\\します。  

   1. 右クリック**Microsoft.Samples.BizTalk.ExtendingMapper.MapperClassLibrary**選択**プロパティ**します。  

   2. 公開キー トークン値をコピーします。  

   3. テキスト エディターで開きます*\<サンプル パス\>* \XML Tools\ExtendingMapper\ExternalAssembly.xml します。  

   4. 選択、 <strong>assemblyname 1.0.0.0、カルチャを = = neutral, PublicKeyToken = 68496d20c737d84b"</strong>属性、および置換、 **PublicKeyToken**パブリック キー トークンの値を値でコピーした手順 c。  

   5. ExternalAssembly.xml を保存して閉じます。  

   > [!NOTE]
   >  このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。  

#### <a name="to-configure-enlist-and-start-the-send-port"></a>送信ポートの構成、参加、開始を行うには  

1. をクリックして**開始**を選択します**すべてのプログラム**を選択します**Microsoft BizTalk Server**、し、 **BizTalk Server 管理**します。  

2. BizTalk Server 管理コンソールで、クリックして展開**BizTalk Server 管理**をクリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開**アプリケーション**します。  

3. クリックして展開**ExtendingMapperApplication**、 をクリックし、**送信ポート**します。  

4. 右側のウィンドウで右クリック**送信ポート**、 をクリックし、**プロパティ**します。  

5. **ExtendingMapperSP – 送信ポートのプロパティ**ダイアログ ボックスで、をクリックして、**送信マップ**ページ。  

    **マップ**列で、ドロップダウン リストから必要なマップを選択します。 をクリック**OK**します。 次の表は、これらのマップについてまとめたものです。  


   |                                 "適用するマップ" プロパティ                                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
   |---------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_CallExternalAssembly        |                                                                                                                                                                                                                                                                                                                                       外部 .NET アセンブリの関数を呼び出す方法を示します、 **Scripting**マップでは、functoid は、この functoid への入力パラメーターに基づいています。 これは、マップ ファイルから処理ロジックを明確に分離するのに役立ちます。 このマップ ファイルは、このサンプルに付属しているアセンブリ MapperClassLibrary.dll を使用します。                                                                                                                                                                                                                                                                                                                                       |
   |           Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineScripts           |                                                                                                                                                                                                                                                                                                                                                                                                                 内でインラインの単純なスクリプトを記述する方法を示します**Scripting** functoid の c#、Visual basic.net、および JScript.NET などの .NET 言語を使用してマップ ファイル。                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |   Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_GlobalVariableInInlineScript    |                                                                                                                                                                                                                                                                                                                                                                                        インライン スクリプトでグローバル変数を使用する方法を示します**Scripting** functoid。 グローバル変数を別の間でマップ ファイルの状態の情報を維持するために通常使用**Scripting** functoid。                                                                                                                                                                                                                                                                                                                                                                                         |
   |            Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineXslt             |                                                                                                                                                                                                                                                                                                                                   未処理のインライン XSLT を使用して、対象ドキュメントに構造を構築する方法について説明内で、 **Scripting** functoid マップにします。 使用して、移行先ドキュメントの一部を構築する**Scripting** functoid とインライン XSLT たびはその他の functoid を使用して、BizTalk マッパーで作成することはできません。                                                                                                                                                                                                                                                                                                                                   |
   |         Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_XsltCalltemplate          |                                                                                                                                                                                                                                内で XSLT 呼び出しテンプレートを使用して、対象ドキュメントに構造を作成する方法を示します、 **Scripting** functoid マップにします。 XSLT 呼び出しテンプレートのインライン XSLT 呼び出しテンプレートにパラメーターを受け入れることができます構造を作成できるようにするにはより有利な点がへの入力パラメーターに基づく、 **Scripting** functoid。 使用して、移行先ドキュメントの一部を構築する**Scripting** functoid とインライン XSLT たびはその他の functoid を使用して、BizTalk マッパーで作成することはできません。                                                                                                                                                                                                                                 |
   | Microsoft.Samples.BizTalk.ExtendingMapper. Scriptor_InlineXsltCallingExternalAssembly |                                                                                                                                                                                                                           インライン XSLT 内から外部 .NET アセンブリを呼び出す方法を示しますの**Scripting** functoid をマップします。 オーバーライドする方法について説明します、**カスタム拡張 XML**カスタム拡張ファイル ExternalAssembly_extxml.xml を呼び出す外部 .NET アセンブリの詳細が含まれる BizTalk マッパー グリッドのプロパティ。 使用して、移行先ドキュメントの一部を構築する**Scripting** functoid とインライン XSLT たびに、他の functoid を使用してマッパー UI で実行することはできません。                                                                                                                                                                                                                           |
   |             Microsoft.Samples.BizTalk.ExtendingMapper. OverridingMapXslt              | BizTalk マッパー ファイルのコンパイル済み XSLT を、カスタム XSLT ファイルで完全にオーバーライドする方法を示します。 オーバーライドすることでこれを行う、**カスタム XSL パス**プロパティと、必要に応じて、**カスタム拡張 XML** BizTalk マッパー グリッドのプロパティ。 用意するカスタム XSLT ファイルは、実行時に使用するプロジェクトのコンパイル済み [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリに含めます。 この場合、マップ ファイル (.btm) の内容は無視されます。 このマップ ファイルに対しておよびの OverridingMapXslt.xml を使用して、**カスタム XSL パス**と**カスタム拡張 XML**プロパティでは、それぞれします。<br /><br /> ソリューション エクスプローラーでマップ ファイルを検証できます。 テンプレート ファイルを編集して使用として使用することができますし、**カスタム XSL パス**BizTalk マッパー グリッドのプロパティ。 BizTalk マッパーを使用してこの XSLT を生成できない場合は、いつでもこのオプションを使用できます。 |

## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順を使用して、Extending Mapper サンプルを実行します。  

#### <a name="to-run-this-sample"></a>このサンプルを実行するには  

1.  入力ファイル ExtendingMapper.xml の入力フォルダーにコピー *\<サンプル パス\>* \XmlTools\ExtendingMapper\In します。  

2.  ファイルの変換およびルーティングする方法に注意してください、 *\<サンプル パス\>* \XmlTools\ExtendingMapper\Out フォルダ。 実行される変換は、適用したマップに基づきます。  

## <a name="see-also"></a>参照  
 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)