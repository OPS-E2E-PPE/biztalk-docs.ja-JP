---
title: カスタム Functoid (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, customizing
- examples, functoids
- functoids, examples
- XML tools
- examples, XML tools
ms.assetid: 9f1eb260-ff62-46f5-a517-57f4e9172b35
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de71eb45faa6c5705cca2ef47061686608126577
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013392"
---
# <a name="custom-functoid-biztalk-server-sample"></a>カスタム Functoid (BizTalk Server サンプル)
カスタム Functoid サンプルは、BizTalk マッパー用のカスタム Functoid を記述する方法を示します。 Functoid は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに追加できます。 Functoid は、BizTalk マッパーにフォーカスがある場合にツールボックスに表示されます。  
  
 カスタム Functoid が認識されるには、BizTalk マッパー アセンブリ内に存在する必要があります。 カスタム Functoid は、C# や Visual Basic などの .NET 準拠の任意の言語で記述できます。  
  
 また、カスタム Functoid は、`Microsoft.BizTalk.BaseFunctoids` クラスから派生し、いくつかのメソッドをオーバーライドすることによって、それらのメソッドの実装を提供する必要があります  (`BaseFunctoid` クラスは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に含まれている Microsoft.BizTalk.BaseFunctoids.dll アセンブリで定義されます)。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 カスタム Functoid サンプルは、いくつかの Functoid を実装します。それぞれの Functoid は、`BaseFunctoid` クラスから派生し、いくつかのメソッドをオーバーライドします。  
  
 カスタム Functoid を実装する場合、そのインライン コードを公開できます。 インライン コードは、Functoid の計算を実行します。 プロジェクトのビルド時に、BizTalk マッパー コンパイラは Functoid からインライン コードを抽出し、コンパイル済みの XSLT に埋め込みます。  
  
 カスタム Functoid がインライン コードを公開しない場合、カスタム Functoid を格納するアセンブリを呼び出す XSLT が BizTalk マッパーによって生成されます。 この場合、カスタム Functoid アセンブリは、XSLT エンジンで検出できるようにグローバル アセンブリ キャッシュ (GAC) で使用可能である必要があります。 また、カスタム Functoid の GUID 属性が一意であることも必要です。 BizTalk マッパーは GUID を使用して、読み込むアセンブリを識別します。  
  
> [!IMPORTANT]
>  カスタム Functoid サンプル コードを再利用して独自の Functoid を実装する場合は、GUID 属性を一意のものに変更する必要があります。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \XmlTools\CustomFunctoid  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報 C# ソース コード。|  
|CBuildArray.bmp|ツールボックス ビットマップ。|  
|CConcat.bmp|ツールボックス ビットマップ。|  
|CExtractArray.bmp|ツールボックス ビットマップ。|  
|Cleanup.bat|アセンブリの展開を解除し、アセンブリをグローバル アセンブリ キャッシュ (GAC) から削除して、CustomFunctoid.dll を削除するために使用されます。|  
|CLongestString.bmp|ツールボックス ビットマップ。|  
|CMultiply.bmp|ツールボックス ビットマップ。|  
|CustomFunctoid.cs|カスタム Functoid C# ソース コード。|  
|CustomFunctoid.csproj|カスタム Functoid C# プロジェクト。|  
|CustomFunctoid.sln|カスタム Functoid ソリューション。|  
|CustomFunctoidResources.resx|カスタム Functoid リソース。|  
|Setup.bat|サンプルのビルド、展開、および起動を行うために使用します。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順に従って、カスタム Functoid サンプルをビルドおよび初期化します。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。  
  
     \<*パスのサンプル*\>\XmlTools\CustomFunctoid  
  
2.  ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
    -   サンプル プロジェクトをビルドします。  
  
    -   生成されたアセンブリを Developer Tools\Mapper Extensions ディレクトリにコピーします。  
  
    -   生成されたアセンブリを GAC に追加します。  
  
        > [!NOTE]
        >  このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順に従って、カスタム Functoid サンプルを実行します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツール**メニューを選択し、 **[ツールボックス アイテムの**します。  
  
2. **ツールボックス アイテムの選択**ダイアログ ボックスで、 **BizTalk マッパー Functoid**タブ。  
  
3. クリックして**リセット**、順にクリックします**OK**します。  
  
   > [!NOTE]
   >  カスタム Functoid でインライン コードが公開されない場合は、アセンブリが GAC で使用可能になっているかどうかを確認してください。  
  
4. **ファイル**メニューの **終了**を閉じる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
5. 開始**Visual Studio コマンド プロンプト**します。  
  
6. コマンド プロンプトで「 **devenv/setup**します。  
  
7. 開始**Microsoft Visual Studio**します。  
  
    カスタム functoid (カスタム累積連結 functoid、最長文字列、配列作成 functoid、および配列抽出 functoid) が表示、**文字列 Functoid**ツールボックス、および累積乗算 functoid のタブを表示、 **累積 Functoid**タブ。  
  
## <a name="removing-this-sample"></a>このサンプルの削除  
 次の手順に従って、カスタム Functoid サンプルを削除します。  
  
#### <a name="to-remove-this-sample"></a>このサンプルを削除するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスから Functoid を削除します。  
  
   > [!WARNING]
   >  Cleanup.bat の実行後に、ツールボックスにまだ古いカスタム Functoid がある場合 (通常は Visual Studio の内部キャッシュのため)、下記の手順に従ってください。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツール**メニューを選択し、 **[ツールボックス アイテムの**します。  
  
   2. **ツールボックス アイテムの選択**ダイアログ ボックスで、 **BizTalk マッパー Functoid**タブ。  
  
   3. 一覧からカスタム Functoid (カスタム累積連結 Functoid、最長文字列、配列作成 Functoid、配列抽出 Functoid、累積乗算) を探します。 それぞれクリックして**チェック ボックスをオン**をクリックして、functoid を削除 **[ok]** します。  
  
      上記の手順でも問題が解決されない場合は、下記の手順に従ってください。  
  
   4. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツールボックス**ツールボックス パレットを表示するマップの編集中のタブ。  
  
   5. ツール ボックスを右クリックして**アイテムの選択**します。  
  
   6. [アイテムの選択] ダイアログ ボックスで、**リセット**、順にクリックします**OK**します。  
  
   7. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のインスタンスをすべて閉じます。  
  
      上記の手順でも問題が解決されない場合は、下記の手順に従ってください。  
  
   8. 開始**Visual Studio コマンド プロンプト**に管理者として。  
  
   9. 実行中の Visual Studio のインスタンスをすべて閉じます。  
  
   10. 次のコマンドを提供します。  
  
        `devenv /resetsettings`  
  
        `devenv /setup`  
  
   11. ツールボックスから不要な Functoid を手動で選択できます。 次に、functoid を右クリックし、クリックして**削除**します。  
  
       上記の手順でも問題が解決されない場合は、下記の手順に従ってください。  
  
   12. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk プロジェクトで、マップを編集しているときに [ツールボックス] タブをクリックして、ツールボックス パレットを開きます。  
  
   13. をクリックして、**累積 Functoid**グループ。  
  
   14. クリックして削除する functoid を右クリックして**削除**または del キーを押します。  
  
   15. をクリックして、**文字列 Functoid**グループ。  
  
   16. クリックして削除する functoid を右クリックして**削除**または del キーを押します。  
  
2. コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。  
  
    \<*パスのサンプル*\>\XmlTools\CustomFunctoid  
  
3. Cleanup.bat ファイルを実行します。処理内容は次のとおりです。  
  
   -   アセンブリが Developer Tools\Mapper Extensions ディレクトリから削除されます。  
  
   -   アセンブリが GAC から削除されます。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 [Microsoft.BizTalk.BaseFunctoids.BaseFunctoid](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.basefunctoid.aspx)  
  
## <a name="see-also"></a>参照  
 [BaseFunctoid の使用](../core/using-basefunctoid.md)   
 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)