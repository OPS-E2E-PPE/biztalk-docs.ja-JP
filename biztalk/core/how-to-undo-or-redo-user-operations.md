---
title: "元に戻すまたはユーザーの操作を再実行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6f47071ee003a896b66120c0fd81a121ab73230
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-undo-or-redo-user-operations"></a>ユーザー操作の取り消しまたはやり直しの方法
元に戻す/やり直しのサポートも、BizTalk マッパーに用意されている便利な操作です。 自分が加えた変更が希望どおりでないか、誤って変更を加えた場合は、	元に戻すを使用して、変更を加えていない以前の状態に徐々に戻り、そこから操作を再開することができます。 やり直しを使用すると、元に戻した編集操作を再適用することができます。 このトピックでは、元に戻すかやり直すことができる操作に関する情報を示します。  
  
> [!IMPORTANT]
>  操作を元に戻すことができるのは、マップで少なくとも 1 つの編集操作を実行した場合のみです。 やり直しは、元に戻すコマンドを使用していない限り使用できません。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="what-can-you-undoredo"></a>元に戻す/やり直しの対象となる操作  
 元に戻す/やり直しの対象となるのは、すべての編集操作です。 それらの操作は次のとおりです。  
  
-   Functoid またはリンクの切り取り/コピー/貼り付け  
  
     単に選択してコピーするのでは、任意の数の項目 (リンクや Functoid) を取り消したり、やり直したりできません。 コピー機能ではマップ上の何も変更されません。  
  
    > [!NOTE]
    >  Functoid の切り取り/コピー/貼り付けする方法については、次を参照してください。[コピー、切り取り、および Functoid を貼り付けする方法](../core/how-to-copy-cut-and-paste-a-functoid.md)です。 切り取り/コピー/貼り付け functoid とリンクする方法の詳細については、次を参照してください。[方法は、コピー、切り取り、貼り付けリンク、および Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)です。  
  
-   送信元ノードから送信先ノード、送信元ノードから Functoid、Functoid から別の Functoid、または Functoid から送信先ノードへのリンク  
  
-   Functoid またはリンクの削除  
  
-   別のグリッド ページへの選択したリンクおよび Functoid の移動  
  
-   グリッド ページの追加、移動、順序変更、または削除  
  
    > [!NOTE]
    >  追加する方法については、移動、順序変更、削除するグリッド ページを参照してください[グリッド ページの順序を変更する方法](../core/how-to-reorder-grid-pages.md)です。  
  
-   マップ作成時における送信元スキーマおよび送信先スキーマの選択  
  
-   送信元/送信先スキーマの置換  
  
    > [!NOTE]
    >  送信元/送信先スキーマの置換する方法については、次を参照してください。[スキーマの置換方法](../core/how-to-replace-schemas.md)です。  
  
-   Functoid の入力パラメーターの構成  
  
    > [!NOTE]
    >  詳細については、次を参照してください。 [Functoid の入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)です。  
  
-   リンクのラベルの設定/編集  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[リンクのラベルを付ける方法](../core/how-to-label-a-link.md)です。  
  
-   Functoid のラベルおよびコメントの設定/編集  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)です。  
  
-   マッパー グリッドに対する "リンクの Namespaces を無視する" および "スクリプトの種類の優先順位" プロパティ  
  
-   あるノードまたは Functoid から別のノードまたは Functoid にリンクの 1 つの端点をドラッグすることによるリンクの置き換え  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[リンクを作成する方法](../core/how-to-create-links.md)です。  
  
-   複数の変更を実行する、**構成\<Functoid > Functoid**  ダイアログ ボックスは、1 つの操作として扱われます。  
  
-   マッパー グリッド内での Functoid およびリンクのドラッグ  
  
    > [!NOTE]
    >  詳細については、次を参照してください。 [、リレーションシップのグリッド ページ間を移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)です。  
  
## <a name="how-can-you-undoredo-any-operation"></a>操作を元に戻す/やり直す方法  
 操作を元に戻すかやり直すには、次のいずれかの方法を使用できます。  
  
-   Visual studio の**編集**メニュー。  
  
-   ツール バーの [元に戻す] アイコンおよび [やり直す] アイコンをクリックする。  
  
-   Ctrl + Z キー (元に戻す場合) および Ctrl + Y キー (やり直す場合) を押す。  
  
## <a name="see-also"></a>参照  
 [グリッド ページの操作](../core/working-with-grid-pages.md)