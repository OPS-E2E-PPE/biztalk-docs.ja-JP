---
title: 元に戻すまたはユーザーの操作を再実行する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ef4122e31bae1c3bd0e107b5a5bb8a4c7405e42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383683"
---
# <a name="how-to-undo-or-redo-user-operations"></a>元に戻すまたはユーザーの操作を再実行する方法
元に戻す/やり直しのサポートはまだ別の便利な操作は、BizTalk マッパーによって提供されます。 変更に満足していない場合、ユーザーが実行または変更を誤って作成した場合は、段階的には、前の状態、およびそこから再開する元に戻すを使用できます。 再実行完了されている編集操作を再適用することができます。 このトピックでは、操作を元に戻す/やり直すをについてを説明します。  
  
> [!IMPORTANT]
>  マップ上の操作が編集を行ったときに少なくとも 1 つのみ、操作を元に戻すことができます。 元に戻すコマンドを使用していない限り、再実行は使用できません。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="what-can-you-undoredo"></a>内容を元に戻す/やり直すでしょうか。  
 元に戻す/やり直すすべての編集操作。 元に戻す/再実行できる操作は次のとおりです。  
  
-   切り取り/コピー/貼り付け functoid やリンク  
  
     元に戻すまたは任意の数の項目 (リンクや functoid) を選択してコピーすることだけで再実行できません。 コピー関数は、マップでは何も変わりません。  
  
    > [!NOTE]
    >  Functoid の切り取り/コピー/貼り付けする方法については、次を参照してください。[コピー、切り取り、および Functoid を貼り付ける方法](../core/how-to-copy-cut-and-paste-a-functoid.md)します。 切り取り/コピー/貼り付けの functoid とリンクする方法の詳細については、次を参照してください。[方法は、コピー、切り取り、貼り付けのリンクおよび Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)します。  
  
-   ソース ノードをリンクする、ターゲット ノードまたは functoid を別の functoid、functoid または functoid からターゲット ノードへのソース ノード  
  
-   Functoid やリンクを削除しています  
  
-   選択したリンクおよび functoid を別のグリッド ページに移動します。  
  
-   追加、移動、順序変更、またはグリッド ページを削除します。  
  
    > [!NOTE]
    >  移動、順序変更、または、グリッド ページの削除が参照を追加する方法については、[グリッド ページの順序を変更する方法](../core/how-to-reorder-grid-pages.md)します。  
  
-   マップを作成するときに、元と送信先スキーマを選択します。  
  
-   送信元/送信先スキーマの置換  
  
    > [!NOTE]
    >  送信元/送信先スキーマの置換する方法については、次を参照してください。[スキーマの置換方法](../core/how-to-replace-schemas.md)します。  
  
-   Functoid の入力パラメーターを構成します。  
  
    > [!NOTE]
    >  詳細については、次を参照してください。 [Functoid 入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)します。  
  
-   リンクのラベルの設定/編集  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[リンクにラベルを付ける方法](../core/how-to-label-a-link.md)します。  
  
-   Functoid のラベルの設定/編集およびコメント  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)します。  
  
-   マッパー グリッドのリンクとスクリプトの種類の優先順位のプロパティの名前空間を無視します。  
  
-   ノードまたは functoid を別のノードまたは functoid からのリンクの 1 つの終点をドラッグしてリンクの置き換えです。  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[リンクを作成する方法](../core/how-to-create-links.md)します。  
  
-   複数の変更を実行する、**構成\<Functoid\> Functoid**ダイアログ ボックスで、1 つの操作として扱われます。  
  
-   Functoid およびマッパー グリッド内のリンクをドラッグします。  
  
    > [!NOTE]
    >  詳細については、次を参照してください。[グリッド ページ間のリレーションシップを移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)します。  
  
## <a name="how-can-you-undoredo-any-operation"></a>方法を元に戻す/やり直す操作でしょうか。  
 元に戻す/やり直す操作は次の方法のいずれかで。  
  
-   Visual studio の**編集**メニュー。  
  
-   ツールバーの取り消しとやり直しのアイコンをクリックします。  
  
-   元に戻すには、CTRL + Z と再実行では、CTRL + Y キーを押します。  
  
## <a name="see-also"></a>参照  
 [グリッド ページの操作](../core/working-with-grid-pages.md)