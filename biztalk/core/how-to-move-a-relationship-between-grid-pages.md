---
title: グリッド ページ間のリレーションシップを移動する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.movetopage
ms.assetid: 185add4d-c876-44b6-b6e0-71c15a9b7c26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5737adcb9159568bfea7c7cdde9dff8015b19706
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255090"
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a>グリッド ページ間で関係を移動する方法
大規模なマップには多数の Functoid とリンクが含まれる場合があり、複数の Functoid に参加しているリンクを識別することが困難です。 このようなシナリオでは、類似した一連の Functoid とリンクを別のグリッド ページに移動してマップを読みやすくすることができます。 このトピックでは、この操作の手順について説明します。  
  
 同じマップ内に限り、次のいずれかの方法で 1 つのグリッド ページから別のグリッド ページに関係を移動できます。  
  
-   使用して、**ページに移動する** ダイアログ ボックス  
  
-   リボンで選択した Functoid (およびリンク) のドラッグ アンド ドロップを使用する  
  
> [!IMPORTANT]
>  1 つ以上の Functoid とそのリンクを移動できます。 関係を移動する場合、その関係に関連付けられたラベル、コメント、および定数値は (正しいプレースホルダーと共に) 維持されます。  
  
> [!IMPORTANT]
>  リンクだけを別のグリッド ペインにドラッグ アンド ドロップすることはできません。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a>[ページに移動] ダイアログ ボックスを使用して関係を移動するには  
  
1.  マップで、リレーションシップの移動元のグリッド ページを選択します。  
  
2.  Functoid またはリンクに移動し、をクリックするリレーションシップを右クリックして**ページに移動する**です。 選択されているすべてのマップ項目と共に関連するリンクと Functoid が移動されることを示すメッセージが表示されます。 **[OK]** をクリックします。  
  
    > [!NOTE]
    >  Visual Studio のメニューで、メッセージのポップアップを無効にするには**ツール**、 をクリックして**オプション**、 をクリックして**BizTalk マッパー**をクリックして**全般**、ボックスをオフにし、**ページに移動**オプション。 [全般] オプションの詳細については、次を参照してください。 [BizTalk マッパーの全般的な設定をカスタマイズする方法](../core/how-to-customize-general-settings-in-biztalk-mapper.md)です。  
  
    > [!TIP]
    >  または、CTRL + M, CTRL + M を開くにをキー、**ページに移動する** ダイアログ ボックス。 マッパーのショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
     ![選択した関係を新しいページに移動](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")  
  
3.  **ページに移動する** ダイアログ ボックスで、クリックして、リレーションシップを移動するターゲットのグリッド ページの選択**OK**です。  
  
    > [!NOTE]
    >  選択して、新しいページを作成することもできます。  **\*(新しいページの追加)**、クリックし、 **OK**です。  
  
    > [!NOTE]
    >  または、Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら A キーを押して、マップに新しいグリッド ページを追加することもできます。 マッパーのショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
     ![ターゲットのグリッド ページの選択](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")  
  
     選択した Functoid とリンク、および関連の Functoid およびリンクが、新しいグリッド ページに移動します。 次のページは、選択した関係 (ページ 3 にあった) がページ 1 に移動したところを示しています。  
  
     ![選択したリレーションシップが新しいページに移動](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a>ドラッグ アンド ドロップを使用して関係を移動するには  
  
1.  マップで、リレーションシップの移動元のグリッド ページを選択します。  
  
2.  別のグリッド ページに移動する Functoid (およびリンク) を選択します。 この操作により、選択した Functoid に接続するすべてのリンクが再帰的に選択されます。  
  
3.  選択した関係を移動先のページ (ページ タブ上) にドラッグします。  
  
    > [!WARNING]
    >  手順 4. を実行するまでマウスを放さないでください。  
  
4.  移動先のグリッド ページにフォーカスが移ったら (前の図では、ページ 1 にフォーカスがあります)、グリッド ページの空のセルに選択したものをドロップします。 選択した関係が新しいグリッド ページに移動しました。  
  
## <a name="see-also"></a>参照  
 [グリッド ページの操作](../core/working-with-grid-pages.md)