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
ms.openlocfilehash: d115e0a0594bc236487cca62c9b61355a8535116
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353404"
---
# <a name="custom-functoid-biztalk-server-sample"></a>カスタム Functoid (BizTalk Server サンプル)
カスタム Functoid サンプルでは、BizTalk マッパー用のカスタム functoid を記述する方法を示します。 Functoid を追加することができます、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。 BizTalk マッパーにフォーカスがときに、ツールボックスに functoid が表示されます。  
  
 カスタム functoid は、認識する BizTalk マッパー アセンブリ内に存在する必要があります。 これは、いずれかで記述できます。C# または Visual Basic などの NET 準拠言語。  
  
 また、カスタム functoid がから派生する必要があります、`Microsoft.BizTalk.BaseFunctoids`クラス、およびは、それらをオーバーライドすることで一部のメソッドの実装を提供する必要があります。 (、`BaseFunctoid`クラスに含まれている Microsoft.BizTalk.BaseFunctoids.dll アセンブリで定義されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 カスタム Functoid サンプルから派生する各いくつかの functoid を実装する、`BaseFunctoid`クラスといくつかのメソッドをオーバーライドします。  
  
 カスタム functoid を実装する場合は、そのインライン コードを公開できます。 インライン コードは、functoid の計算を実行します。 BizTalk マッパーのコンパイラでは、functoid からインライン コードを抽出し、プロジェクトをビルドするときにコンパイルされた XSLT に埋め込みます。  
  
 カスタム functoid でインライン コードが公開されない場合、BizTalk マッパーには、カスタム functoid が存在するアセンブリを呼び出す XSLT が生成されます。 この場合は、カスタム functoid アセンブリがあることをグローバル アセンブリ キャッシュ (GAC) に、XSLT エンジンが検索できるようにする必要があります。 カスタム functoid は、一意の GUID 属性も必要です。 BizTalk マッパーでは、どのアセンブリを読み込むを識別するのに GUID を使用します。  
  
> [!IMPORTANT]
>  独自の functoid を実装するためにカスタム Functoid サンプル コードを再利用する場合は、一意である 1 つに GUID 属性を変更することを確認する必要があります。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \XmlTools\CustomFunctoid  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|AssemblyInfo.cs|アセンブリ情報 c# ソース コード。|  
|CBuildArray.bmp|ツールボックス ビットマップ。|  
|CConcat.bmp|ツールボックス ビットマップ。|  
|CExtractArray.bmp|ツールボックス ビットマップ。|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除し、CustomFunctoid.dll を削除するために使用します。|  
|CLongestString.bmp|ツールボックス ビットマップ。|  
|CMultiply.bmp|ツールボックス ビットマップ。|  
|CustomFunctoid.cs|カスタム functoid c# ソース コードです。|  
|CustomFunctoid.csproj|カスタム functoid c# プロジェクト。|  
|CustomFunctoid.sln|カスタム functoid ソリューション。|  
|CustomFunctoidResources.resx|カスタム functoid リソース。|  
|Setup.bat|ビルド、配置、およびサンプルを開始するために使用します。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 次の手順を使用して、ビルドして、カスタム Functoid サンプルを初期化します。  
  
#### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1.  コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。  
  
     \<*パスのサンプル*\>\XmlTools\CustomFunctoid  
  
2.  ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
    -   サンプル プロジェクトをビルドします。  
  
    -   生成されたアセンブリを Developer tools \mapper Extensions ディレクトリにコピーします。  
  
    -   生成されたアセンブリを GAC に追加します。  
  
        > [!NOTE]
        >  エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 カスタム Functoid サンプルを実行するのにには、次の手順を使用します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツール**メニューを選択し、 **ツールボックス アイテムの**します。  
  
2. **ツールボックス アイテムの選択**ダイアログ ボックスで、 **BizTalk マッパー Functoid**タブ。  
  
3. クリックして**リセット**、順にクリックします**OK**します。  
  
   > [!NOTE]
   >  カスタム functoid でインライン コードが公開されない場合は、そのアセンブリを GAC に利用可能になってを確認します。  
  
4. **ファイル**メニューの **終了**を閉じる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
5. 開始**Visual Studio コマンド プロンプト**します。  
  
6. コマンド プロンプトで「 **devenv/setup**します。  
  
7. 開始**Microsoft Visual Studio**します。  
  
    カスタム functoid (カスタム累積連結 functoid、最長文字列、配列作成 functoid、および配列抽出 functoid) が表示、**文字列 Functoid**ツールボックス、および累積乗算 functoid のタブを表示、 **累積 Functoid**タブ。  
  
## <a name="removing-this-sample"></a>このサンプルの削除  
 カスタム Functoid サンプルを削除するのにには、次の手順を使用します。  
  
#### <a name="to-remove-this-sample"></a>このサンプルを削除するには  
  
1. Functoid を削除、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。  
  
   > [!WARNING]
   >  Cleanup.bat を実行した後は、まだ古いカスタム functoid を (おそらく内部キャッシュのため Visual Studio によって)、ツールボックスを表示、以下の手順に従います。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツール**メニューを選択し、 **ツールボックス アイテムの**します。  
  
   2. **ツールボックス アイテムの選択**ダイアログ ボックスで、 **BizTalk マッパー Functoid**タブ。  
  
   3. リスト内のカスタム functoid (カスタム累積連結 functoid、最長文字列、配列作成 functoid、配列抽出 functoid、および累積乗算) を検索します。 それぞれクリックして**チェック ボックスをオン**をクリックして、functoid を削除 **[ok]** します。  
  
      上記の手順が機能しない場合は、次の手順の下。  
  
   4. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツールボックス**ツールボックス パレットを表示するマップの編集中のタブ。  
  
   5. ツール ボックスを右クリックして**アイテムの選択**します。  
  
   6. [アイテムの選択] ダイアログ ボックスで、**リセット**、順にクリックします**OK**します。  
  
   7. インスタンスをすべて閉じます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
      上記の手順が機能しない場合は、次の手順の下。  
  
   8. 開始**Visual Studio コマンド プロンプト**に管理者として。  
  
   9. Visual Studio の実行中のすべてのインスタンスを閉じます。  
  
   10. 次のコマンドを提供します。  
  
        `devenv /resetsettings`  
  
        `devenv /setup`  
  
   11. ツールボックスから不要な functoid を手動で選択することができます。 次に、functoid を右クリックし、クリックして**削除**します。  
  
       上記の手順が機能しない場合は、次の手順の下。  
  
   12. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、ツールボックス パレットを表示するマップの編集中に、[ツールボックス] タブをクリックします。  
  
   13. をクリックして、**累積 Functoid**グループ。  
  
   14. クリックして削除する functoid を右クリックして**削除**または del キーを押します。  
  
   15. をクリックして、**文字列 Functoid**グループ。  
  
   16. クリックして削除する functoid を右クリックして**削除**または del キーを押します。  
  
2. コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。  
  
    \<*パスのサンプル*\>\XmlTools\CustomFunctoid  
  
3. Cleanup.bat は、次の操作を実行するファイルを実行します。  
  
   -   Developer tools \mapper Extensions ディレクトリからアセンブリを削除します。  
  
   -   GAC からアセンブリを削除します。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 [Microsoft.BizTalk.BaseFunctoids.BaseFunctoid](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.basefunctoid.aspx)  
  
## <a name="see-also"></a>参照  
 [BaseFunctoid の使用](../core/using-basefunctoid.md)   
 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)