---
title: 追加して、Visual Studio のツールボックスからカスタム Functoid の削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e3493608606df11a5237287a89cbf79d384800a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360905"
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a>追加して、Visual Studio のツールボックスからカスタム Functoid の削除
このトピックでは、カスタム functoid を追加およびからカスタム functoid を削除する方法を説明します、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。  
  
## <a name="adding-custom-functoids-to-visual-studio"></a>Visual Studio にカスタム Functoid の追加  
 カスタム functoid を追加する必要があります、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス前に、これらは、マップで使用できます。 カスタム functoid を追加するのにには、次の手順を使用します。  
  
#### <a name="to-add-a-custom-functoid"></a>カスタム functoid を追加するには  
  
1. Functoid を追加、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。  
  
   1. Windows エクスプ ローラーを使用して、カスタム functoid を実装するアセンブリを検索します。  
  
   2. アセンブリをコピー、 \< *BizTalk Server のインストール フォルダー*\>**\Developer Tools\Mapper 拡張**ディレクトリ。 これは、BizTalk マッパーがカスタム functoid を検索する場所です。  
  
   3. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。  
  
   4. **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブ。  
  
   5. クリックして**リセット**、順にクリックします**OK**します。 このプロセスには数分かかる場合があります。  
  
       カスタム functoid ツールボックスのタブの各カテゴリの下に表示されます。  
  
      \- または -  
  
   6. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。  
  
   7. **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブ。  
  
   8. クリックして**リセット**、順にクリックします**OK**します。  
  
      > [!NOTE]
      >  カスタム functoid でインライン コードが公開されない場合は、グローバル アセンブリ キャッシュに利用可能になってそのアセンブリを確認します。  
  
   9. **ファイル** メニューのをクリックして**終了**を閉じる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
   10. 開始**Visual Studio コマンド プロンプト**します。  
  
   11. コマンド プロンプトで「 **devenv/setup**します。  
  
   12. 開始**Microsoft Visual Studio**します。  
  
        カスタム functoid は、適切なタブに表示されます。  
  
2. アセンブリをグローバル アセンブリ キャッシュに追加します。 アセンブリにのみインライン型の functoid が含まれている場合は、この手順をスキップすることができます。  
  
   1.  開始**Visual Studio コマンド プロンプト**します。  
  
   2.  アセンブリを含むフォルダーに切り替えます。  
  
   3.  コマンド プロンプトで「 **gacutil/if < assembly_path >** します。 たとえば、アセンブリ名が FunctoidLibrary.dll の場合は、入力**gacutil/if FunctoidLibrary.dll**します。  
  
   4.  入力が完了したら、**終了**します。  
  
## <a name="removing-custom-functoids-from-visual-studio"></a>Visual Studio からのカスタム Functoid の削除  
 カスタム functoid を削除するのにには、次の手順を使用します。  
  
#### <a name="to-remove-a-custom-functoid"></a>カスタム functoid を削除するには  
  
1. Functoid を削除、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。  
  
   1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。  
  
   2. **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブ。  
  
   3. カスタム functoid を一覧で検索、**削除**チェック ボックスをオンにして **[ok]** します。  
  
      \- または -  
  
   4. マップを編集中に、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクト をクリックして、**ツールボックス**タブをツールボックス パレットを開きます。  
  
   5. カスタム functoid を含む functoid グループをクリックします。  
  
   6. 削除するをクリックする functoid を右クリックして**削除**または del キーを押します。  
  
2. Functoid アセンブリの削除、 **Developer tools \mapper Extensions**ディレクトリ。  
  
   > [!CAUTION]
   >  アセンブリにアクティブな functoid が含まれている場合は削除されません。 そうと、その他のマップが解除されます。  
  
   1. Windows エクスプ ローラーを起動しに移動し、 **Developer tools \mapper Extensions**ディレクトリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
   2. 削除の functoid を含むアセンブリを右クリックし、をクリックし、**削除**ファイルを削除します。  
  
3. Functoid のアセンブリをグローバル アセンブリ キャッシュから削除します。 アセンブリにのみインライン型の functoid が含まれている場合は、この手順をスキップすることができます。  
  
   > [!CAUTION]
   >  アセンブリにアクティブな functoid が含まれている場合、グローバル アセンブリ キャッシュから削除されません。 そうと、その他のマップが解除されます。  
  
   1.  開始**Visual Studio コマンド プロンプト**します。  
  
   2.  コマンド プロンプトで「 **gacutil/u < assembly_display_name >** します。 たとえば、アセンブリ名が FunctoidLibrary.dll の場合は、入力**gacutil/if FunctoidLibrary**します。  
  
   3.  入力が完了したら、**終了**します。  
  
## <a name="see-also"></a>参照  
 [カスタム Functoid の開発](../core/developing-custom-functoids.md)