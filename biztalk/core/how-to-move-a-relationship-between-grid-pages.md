---
title: グリッド ページ間のリレーションシップを移動する方法 |Microsoft Docs
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
ms.openlocfilehash: da495b073df7f76ba60946f66a4a40b697c25793
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335973"
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a>グリッド ページ間のリレーションシップを移動する方法
大規模なマップは、多くの functoid とリンクで、複数の functoid に参加するリンクを識別するための難しいことがあります。 このようなシナリオでは、functoid およびリンクのようなセットは、マップを読みやすくする別のグリッド ページに移動する可能性があります。 このトピックで、操作を実行する手順について説明します。  
  
 間のみ、同じマップ内の 1 つのグリッド ページからリレーションシップを移動するには、次の方法のいずれかで。  
  
-   使用して、**ページに移動する** ダイアログ ボックス  
  
-   ドラッグ アンド ドロップのリボンで選択した functoid (およびリンク) を使用します。  
  
> [!IMPORTANT]
>  1 つまたは複数の functoid とそのリンクを移動することができます。 リレーションシップ、ラベル、コメント、および (正しいプレース ホルダー) と定数の値を移動すると関連付けられているリレーションシップが保持されます。  
  
> [!IMPORTANT]
>  別のグリッド ページにのみリンクをドラッグ アンド ドロップすることはできません。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a>ページに移動 ダイアログ ボックスを使用してリレーションシップを移動するには  
  
1.  マップでは、関係を移動するグリッド ページを選択します。  
  
2.  Functoid またはリンクをクリックして移動するリレーションシップを右クリックして**ページに移動する**します。 すべて、選択したマップ項目 (s) との関連リンクと functoid が移動されることを示すメッセージが表示されます。 **[OK]** をクリックします。  
  
    > [!NOTE]
    >  Visual Studio のメニューで、メッセージのポップアップを無効にするには**ツール**、 をクリックして**オプション**、 をクリックして**BizTalk マッパー**、 をクリックして**全般**、オフにし、**ページに移動**オプション。 [全般] オプションの詳細については、次を参照してください。 [BizTalk マッパーの全般設定をカスタマイズする方法](../core/how-to-customize-general-settings-in-biztalk-mapper.md)します。  
  
    > [!TIP]
    >  または、CTRL + M, CTRL + M を開くをキー、**ページに移動する** ダイアログ ボックス。 マッパーのショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。  
  
     ![選択した関係を新しいページに移動](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")  
  
3.  **ページに移動する** ダイアログ ボックスで、リレーションシップを移動し、クリックするターゲットのグリッド ページを選択します。 **OK**。  
  
    > [!NOTE]
    >  選択して、新しいページを作成することもできます。  **\*(新しいページを追加)**、 をクリックし、 **OK**します。  
  
    > [!NOTE]
    >  または、CTRL + M, CTRL + A マップで新しいグリッド ページを追加するキーを押すことができます。 マッパーのショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)します。  
  
     ![ターゲットのグリッド ページの選択](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")  
  
     関連の functoid およびリンクと共に選択した functoid/リンクでは、新しいグリッド ページに移動されます。 次の図は、選択したリレーションシップ (ページ 3 では) を 1 ページに移動します。  
  
     ![選択したリレーションシップは新しいページに移動](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a>ドラッグ アンド ドロップを使用してリレーションシップを移動するには  
  
1.  マップでは、関係を移動するグリッド ページを選択します。  
  
2.  Functoid (および別のグリッド ページに移動する link(s)) を選択します。 この再帰的には、選択範囲の functoid に接続するすべてのリンクを選択します。  
  
3.  リレーションシップを移動する ([ページ] タブで) ページに、選択をドラッグします。  
  
    > [!WARNING]
    >  手順 4. を実行するまでマウスを解放できません。  
  
4.  ときに、ターゲットのグリッド ページにフォーカスが移ったら (上記の図では、1 ページにフォーカスが)、グリッド ページで、空のセルの選択項目をドロップします。 選択したリレーションシップは、新しいグリッド ページに移動されます。  
  
## <a name="see-also"></a>参照  
 [グリッド ページの操作](../core/working-with-grid-pages.md)