---
title: コピー、切り取り、および Functoid を貼り付けする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825847e4-87db-4b40-8e5d-5b5b1c79c6de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9af3662fb866eb09c1dcb2516279ca097cc998f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249530"
---
# <a name="how-to-copy-cut-and-paste-a-functoid"></a>コピー、切り取り、および貼り付けする方法について
BizTalk マッパーのコピー機能、切り取り機能、および貼り付け機能により、Functoid を再利用できます。 マップで、1 つ以上の Functoid をあるグリッド ページから別のグリッド ページにコピー、切り取り、および貼り付けることができます。 このトピックでは、これらの操作を実行するための手順について説明します。  
  
 コピー/貼り付け機能は、Functoid を再利用するときに使用できます。 また、Functoid を既存の場所から削除し、新しい場所に移動するときは、切り取り/貼り付け機能を使用できます。  
  
> [!IMPORTANT]
>  Functoid のコピーを選択すると、Functoid、ラベル、コメント、および定数入力がプレースホルダー インデックスと共にコピーされます。 同様に、Functoid の切り取りを選択すると、Functoid、ラベル、コメント、および定数入力がプレースホルダー インデックスと共に切り取られます。 しかし、切り取りを選択した後に選択内容を貼り付けると、Functoid のみが維持され、孤立したリンクは削除されます。 ラベル、コメント、定数入力、およびプレースホルダー インデックスは維持されません。  
  
 別の Functoid またはスキーマ ノードにリンクしている Functoid のみを選択した場合、その Functoid のみが切り取られるかまたはコピーされ、リンクの切り取りやコピーは行われません。 マップ内の他の Functoid またはスキーマ ノードにリンクした Functoid を切り取った場合、切り取った Functoid へのリンクは削除されます。  
  
 Functoid のコピー/切り取り操作は次の場所で行うことができます。  
  
-   マップの同じグリッド ページ内  
  
-   同じマップのグリッド ページ間  
  
-   Visual Studio のインスタンス間  
  
 切り取り/貼り付け操作は元に戻したり、やり直したりすることができます。 詳細については、次を参照してください。[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-copy-and-paste-a-functoid"></a>Functoid のコピーおよび貼り付けを行うには  
  
1.  ソリューション エクスプローラーで、BizTalk プロジェクトを開き、マップをダブルクリックして BizTalk マッパーで開きます。  
  
2.  コピーする Functoid を選択します。 複数の functoid を選択するには、Ctrl キーを押しながら他の functoid をクリックします。  
  
    > [!NOTE]
    >  "リボン選択" 操作を使用して、複数のリンクや Functoid を選択できます。 詳細については、次を参照してください。[および Functoid を複数のリンクを選択する方法](../core/how-to-select-multiple-links-and-functoids.md)です。  
  
3.  選択範囲を右クリックし、をクリックして**コピー**です。 いずれかをクリックすることができます、**コピー** Visual studio の**編集**メニューやキーボードの ctrl キーを押しながら C キーを押します。  
  
    > [!NOTE]
    >  キーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
4.  Functoid を貼り付ける場所にカーソルを置きます。  
  
5.  グリッド ページを右クリックし、をクリックして**貼り付け**です。 いずれかをクリックすることができます、**貼り付け**Visual studio の**編集**メニューやキーボードの ctrl キーを押しながら V キーを押します。 選択した Functoid または Functoid のグループが新しい場所に表示されます。  
  
### <a name="to-cut-and-paste-a-functoid"></a>Functoid の切り取りおよび貼り付けを行うには  
  
1.  ソリューション エクスプローラーで、BizTalk プロジェクトを開き、マップをダブルクリックして BizTalk マッパーで開きます。  
  
2.  切り取る Functoid を選択します。 複数の functoid を選択するには、Ctrl キーを押しながら他の functoid をクリックします。  
  
3.  選択範囲を右クリックし、をクリックして**切り取り**です。 いずれかをクリックすることができます、**切り取り**Visual studio の**編集**メニューやキーボードの ctrl キーを押しながら X キーを押します。  
  
    > [!NOTE]
    >  キーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
4.  Functoid を貼り付ける場所にカーソルを置きます。  
  
5.  グリッド ページを右クリックし、をクリックして**貼り付け**です。 いずれかをクリックすることができます、**貼り付け**Visual studio の**編集**メニューやキーボードの ctrl キーを押しながら V キーを押します。 選択した Functoid または Functoid のグループが既存の場所から削除され、新しい場所に表示されます。  
  
## <a name="see-also"></a>参照  
 [Functoid を使用して、複雑なマッピングを作成するには](../core/using-functoids-to-create-more-complex-mappings.md)