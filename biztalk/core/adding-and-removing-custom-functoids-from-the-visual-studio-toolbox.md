---
title: "追加して、Visual Studio のツールボックスからカスタム Functoid の削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b34d546de0bbb2a79300c4f672bdfcecdab5958
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a>Visual Studio ツールボックスに対するカスタム Functoid の追加と削除
ここでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに対し、カスタム Functoid を追加する方法と削除する方法について説明します。  
  
## <a name="adding-custom-functoids-to-visual-studio"></a>Visual Studio へのカスタム Functoid の追加  
 カスタム Functoid をマップ内で使用するには、事前に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに追加しておく必要があります。 カスタム Functoid を追加するには、次の操作を行います。  
  
#### <a name="to-add-a-custom-functoid"></a>カスタム Functoid を追加するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに Functoid を追加します。  
  
    1.  Windows エクスプローラーを使用して、カスタム Functoid が実装されているアセンブリを探します。  
  
    2.  アセンブリをコピー、 \< *BizTalk Server のインストール フォルダー*>**\Developer Tools\Mapper 拡張**ディレクトリ。 BizTalk マッパーは、このフォルダーに対してカスタム Functoid を検索します。  
  
    3.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。  
  
    4.  **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブです。  
  
    5.  をクリックして**リセット**、クリックして**[ok]**です。 この処理は時間がかかる場合があります。  
  
         カスタム Functoid が、各カテゴリを示すタブの下にあるツールボックスに表示されます。  
  
     \- または -  
  
    1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。  
  
    2.  **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブです。  
  
    3.  をクリックして**リセット**、クリックして**[ok]**です。  
  
        > [!NOTE]
        >  カスタム Functoid でインライン コードが公開されない場合は、アセンブリがグローバル アセンブリ キャッシュで使用可能になっているかどうかを確認してください。  
  
    4.  **ファイル** メニューのをクリックして**終了**を閉じる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。  
  
    5.  開始**Visual Studio コマンド プロンプト**です。  
  
    6.  コマンド プロンプトで次のように入力します。 **devenv/setup**です。  
  
    7.  開始**Microsoft Visual Studio**です。  
  
         カスタム Functoid が、該当するタブに表示されます。  
  
2.  アセンブリをグローバル アセンブリ キャッシュに追加します。 アセンブリにインライン型の Functoid だけが含まれる場合は、この手順を省略できます。  
  
    1.  開始**Visual Studio コマンド プロンプト**です。  
  
    2.  アセンブリを含むフォルダーに切り替えます。  
  
    3.  コマンド プロンプトで次のように入力します。 **gacutil/if < assembly_path >**です。 たとえば、アセンブリ名が FunctoidLibrary.dll の場合は、入力**gacutil/if FunctoidLibrary.dll**です。  
  
    4.  入力が完了したら、**終了**です。  
  
## <a name="removing-custom-functoids-from-visual-studio"></a>Visual Studio からのカスタム Functoid の削除  
 カスタム Functoid を削除するには、次の操作を行います。  
  
#### <a name="to-remove-a-custom-functoid"></a>カスタム Functoid を削除するには  
  
1.  Functoid を削除、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスします。  
  
    1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。  
  
    2.  **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブです。  
  
    3.  Select の一覧で、カスタム functoid を検索、**削除**チェック ボックスをクリックして**[ok]**です。  
  
     \- または -  
  
    1.  マップを編集中に、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをクリックして、**ツールボックス**タブ、ツールボックス パレットをします。  
  
    2.  カスタム Functoid を含む Functoid グループをクリックします。  
  
    3.  削除、およびをクリックする functoid を右クリックして**削除**または del キーを押します。  
  
2.  Functoid アセンブリが削除、 **Developer tools \mapper Extensions**ディレクトリ。  
  
    > [!CAUTION]
    >  アセンブリにアクティブな Functoid が含まれている場合は、アセンブリを削除しないでください。 削除すると、他のマップが壊れます。  
  
    1.  Windows エクスプ ローラーを起動しに移動し、 **Developer tools \mapper Extensions**ディレクトリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
    2.  削除した functoid を含むアセンブリを右クリックし、をクリックして**削除**ファイルを削除します。  
  
3.  グローバル アセンブリ キャッシュから Functoid アセンブリが削除されます。 アセンブリにインライン型の Functoid だけが含まれる場合は、この手順を省略できます。  
  
    > [!CAUTION]
    >  アセンブリにアクティブな Functoid が含まれている場合は、グローバル アセンブリ キャッシュからアセンブリを削除しないでください。 削除すると、他のマップが壊れます。  
  
    1.  開始**Visual Studio コマンド プロンプト**です。  
  
    2.  コマンド プロンプトで次のように入力します。 **gacutil/u < assembly_display_name >**です。 たとえば、アセンブリ名が FunctoidLibrary.dll の場合は、入力**gacutil/if FunctoidLibrary**です。  
  
    3.  入力が完了したら、**終了**です。  
  
## <a name="see-also"></a>参照  
 [カスタム Functoid の開発](../core/developing-custom-functoids.md)