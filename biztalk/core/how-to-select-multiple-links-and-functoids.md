---
title: 複数のリンクおよび Functoid を選択する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9ae50cb-c212-48f3-9dfb-74df282645c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dbc88252719a59780f5971a4f68990057b130b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383973"
---
# <a name="how-to-select-multiple-links-and-functoids"></a>複数のリンクおよび Functoid を選択する方法
マップの functoid やリンクのグループに対して同じ操作を実行する場合は、同時にすべての functoid やリンクには、そのグループを選択できます。 このトピックでは、次の操作を実行する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="why-do-you-need-to-bulk-select-linksfunctoids"></a>一括選択のリンクおよび functoid に必要な理由  
 一括選択できますリンクや functoid には、次のいずれかの。  
  
-   コピーまたは切り取りと同じグリッド ページまたは同じマップ内の別のグリッド ページで選択内容を貼り付けます。  
  
    > [!NOTE]
    >  コピー、切り取り、貼り付けのリンクおよび functoid については、次を参照してください。[方法は、コピー、切り取り、貼り付けのリンクおよび Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)します。  
  
-   グリッド ページ間で移動します。  
  
    > [!NOTE]
    >  1 つのグリッド ページ間のリレーションシップを移動する方法については、次を参照してください。[グリッド ページ間のリレーションシップを移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)します。  
  
-   Functoid およびリンクの選択範囲の共通プロパティを編集します。  
  
    > [!NOTE]
    >  コメントと functoid およびリンクのラベルを設定する方法については、次を参照してください。[リンクにラベルを付ける方法](../core/how-to-label-a-link.md)または[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)。  
  
-   複数のリンクや functoid を 1 つの手順で削除しています  
  
    > [!NOTE]
    >  Functoid を削除する方法については、次を参照してください。 [Functoid を削除する方法](../core/how-to-delete-functoids.md)します。  
  
## <a name="to-select-multiple-links-and-functoids"></a>複数のリンクおよび functoid を選択するには  
 一括選択できます functoid やリンクで、次の方法のいずれか。  
  
-   リンクまたは functoid をクリックします。 CTRL キー、キーを押しながら他のリンクまたは functoid を選択する をクリックします。  
  
     次の図は、選択した functoid およびリンクの強調表示されます。  
  
     ![Functoid およびリンクを選択する一括](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois & リンク")  
  
-   マップ画面で、マウスをドラッグします。 選択範囲内の functoid が強調表示されます。  
  
     ![Functoid の矩形選択](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")  
  
-   ドラッグの組み合わせを使用することができ、ctrl キーをクリックします。 マップ画面上にマウスをドラッグし、その範囲の functoid やリンクを選択します。 CTRL キー、キーを押しながら functoid や選択範囲の外側にあるリンクをクリックします。  
  
## <a name="to-select-all-links-and-functoids-on-the-grid-page"></a>すべてのリンクと functoid をグリッド ページを選択するには  
 次の方法のいずれかでは、すべての functoid およびマッパー グリッド ページ上のリンクを選択できます。  
  
-   グリッド ページで任意の場所を右クリックし、をクリックして**すべて選択**します。  
  
-   グリッド ページで任意の場所 をクリックし、キーボードの CTRL + A キーを押します。  
  
-   グリッド ページで、任意の場所をクリックします。 Visual Studio のメニューからクリックして**編集**、順にクリックします**すべて選択**します。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードとフィールド マッピングを指定する](../core/using-links-to-specify-record-and-field-mappings.md)