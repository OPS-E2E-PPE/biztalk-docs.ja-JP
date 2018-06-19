---
title: 複数のリンクおよび Functoid を選択する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 8885fe33d0c3a2dc081fbca66a398003c3e21913
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255226"
---
# <a name="how-to-select-multiple-links-and-functoids"></a>複数のリンクおよび Functoid を選択する方法
マップ内の Functoid およびリンクのグループに対して同じ操作を実行したい場合は、複数の Functoid およびリンクをグループとして同時に選択することができます。 このトピックでは、次の操作を実行する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
## <a name="why-do-you-need-to-bulk-select-linksfunctoids"></a>リンクおよび Functoid を一括選択する理由  
 次のどちらかの状況では、リンクおよび Functoid を一括選択できます。  
  
-   同じグリッド ページまたは同じマップ内の他のグリッド ページで、選択項目のコピーまたは切り取りと貼り付けを実行する場合。  
  
    > [!NOTE]
    >  コピー、切り取り、および貼り付けのリンクおよび functoid をする方法については、次を参照してください。[方法は、コピー、切り取り、貼り付けリンク、および Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)です。  
  
-   グリッド ページ間で選択項目を移動する場合。  
  
    > [!NOTE]
    >  グリッド ページ間でリレーションシップを移動する方法については、次を参照してください。 [、リレーションシップのグリッド ページ間を移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)です。  
  
-   選択した Functoid およびリンクの共通プロパティを編集する場合。  
  
    > [!NOTE]
    >  Functoid およびリンクのコメントとラベルを設定する方法については、次を参照してください。[リンクのラベルを付ける方法](../core/how-to-label-a-link.md)または[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)です。  
  
-   複数のリンクや Functoid を一度に削除する場合。  
  
    > [!NOTE]
    >  Functoid を削除する方法については、次を参照してください。 [Functoid を削除する方法](../core/how-to-delete-functoids.md)です。  
  
## <a name="to-select-multiple-links-and-functoids"></a>複数のリンクおよび Functoid を選択するには  
 リンクおよび Functoid は、次のいずれかの方法で一括選択できます。  
  
-   リンクまたは Functoid をクリックします。 Ctrl キーを押しながら、選択したい他のリンクまたは Functoid をクリックします。  
  
     次の図では、選択済みの Functoid およびリンクが強調表示されています。  
  
     ![Functoid およびリンクを選択する一括](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois & へのリンク")  
  
-   マップ画面上でマウスをドラッグします。 選択した範囲内の Functoid が強調表示されます。  
  
     ![Functoid の矩形選択](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")  
  
-   ドラッグと Ctrl + クリックを組み合わせて使用することもできます。 マップ画面上でマウスをドラッグして、その範囲内の Functoid またはリンクを選択します。 Ctrl キーを押しながら、選択範囲の外側にあるリンクまたは Functoid をクリックします。  
  
## <a name="to-select-all-links-and-functoids-on-the-grid-page"></a>グリッド ページ内のすべてのリンクと Functoid を選択するには  
 マッパーのグリッド ページにあるすべての Functoid とリンクは、次のいずれかの方法で一括選択できます。  
  
-   グリッド ページの任意の場所を右クリックし、をクリックして**すべて選択**です。  
  
-   グリッド ページの任意の場所をクリックし、Ctrl キーを押しながら A キーを押します。  
  
-   グリッド ページの任意の場所をクリックします。 Visual Studio のメニューからをクリックして**編集**、クリックして**すべて選択**です。  
  
## <a name="see-also"></a>参照  
 [リンクを使用してレコードを指定してフィールドのマッピング](../core/using-links-to-specify-record-and-field-mappings.md)