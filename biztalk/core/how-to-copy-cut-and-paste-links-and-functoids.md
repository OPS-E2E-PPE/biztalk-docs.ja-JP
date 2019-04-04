---
title: '方法: コピー、切り取り、およびリンクおよび Functoid を貼り付ける |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80b4792a-5ff6-4603-96cd-b3d3d530c12f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dcce057f4c3e04eb4974ccd7f8833e2dab8e580
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016041"
---
# <a name="how-to-copy-cut-and-paste-links-and-functoids"></a>リンクと Functoid をコピー、切り取り、および貼り付けする方法
BizTalk マッパーのコピー/切り取り/貼り付け機能を利用すると、リレーションシップを再利用できます。 このトピックでは、マップ内の Functoid やリンクのコピー、切り取り、および貼り付けの手順を説明します。  
  
 コピー/貼り付け機能は、Functoid やリンクを再利用するときに使用します。 また、既存の場所から選択したものを削除して別の場所に移動するときは、切り取り/貼り付け機能を使用します。  
  
> [!IMPORTANT]
>  切り取り/貼り付けと移動は、よく似ていますが、 別の機能です。 切り取りを選択したときは、選択範囲の Functoid やリンクのみがソース グリッド ページから削除されます。 移動を選択したときは、そのリレーションシップ内のすべての Functoid とリンクが (ユーザーが選択したかどうかにかかわらず)、再帰的に、ソース グリッド ページから削除されます。 リレーションシップの移動の詳細については、[グリッド ページ間のリレーションシップを移動する方法](../core/how-to-move-a-relationship-between-grid-pages.md)を参照してください。  
  
 してコピー/切り取り一連の functoid やリンク、functoid、ラベル、コメント、および定数の値 (正しいプレース ホルダー) と共にに関連付けられているセットを保持すること。  
  
 コピー/切り取りを実行できるのは、次のマップ項目のみです。  
  
- ソースからターゲット スキーマへのリンクします。  
  
- Functoid からスキーマ ノードへのリンク ("Functoid" もリンクと共に選択された場合のみ)  
  
- Functoid から Functoid へのリンク (両方の Functoid がリンクと共に選択された場合のみ)  
  
  Functoid やリンクのコピー/切り取りは、次の場所で実行できます。  
  
- マップの同じグリッド ページ内  
  
- 同じマップのグリッド ページ間  
  
- Visual Studio の同じインスタンス内のマップ間  
  
- Visual Studio のインスタンスから別のインスタンス  
  
  切り取り/貼り付け操作は元に戻したり、やり直したりすることができます。 詳細については、[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)を参照してください。  
  
  これに加えて、リンクを貼り付けるときは次の点を考慮する必要があります。  
  
- ソース スキーマ/ターゲット スキーマ間のリンクの貼り付けができるのは、そのリンクのソース ノードおよびターゲット ノードの XPath と同一の XPath を持つソース ノードおよびターゲット ノードが、貼り付け先のマップに存在している場合のみです。  
  
- ソース スキーマ/ターゲット スキーマ間のリンクの貼り付けができるのは、前述のソース ノードとターゲット ノードの間にリンクが 1 つも存在しない場合のみです。  
  
- Functoid からターゲット スキーマへのリンクの貼り付けができるのは、そのリンクのターゲット ノードの XPath と同じ XPath を持つターゲット ノードが存在する場合のみです。  
  
- ソース スキーマから Functoid へのリンクの貼り付けができるのは、そのリンクのソース ノードの XPath と同じ XPath を持つソース ノードが存在する場合のみです。  
  
> [!NOTE]
>  複数のアイテム (リンクや Functoid) を選択し、その一部の切り取りまたはコピーができない場合、切り取り/コピー コマンドを実行すると、Visual Studio のステータス バーに "Some of the selected items could not be cut/copied" という警告メッセージが表示されます。 また、メッセージには関連する詳細情報も表示されます。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-copy-and-paste-a-relationship"></a>リレーションシップをコピーして貼り付けるには  
  
1.  ソリューション エクスプローラーで、BizTalk プロジェクトを開き、マップをダブルクリックして BizTalk マッパーで開きます。  
  
2.  コピーする Functoid やリンクを選択します。  
  
    > [!TIP]
    >  Ctrl キーを押しながら目的の functoid を選択するか、複数のリンクにまたがってマウスをドラッグ アンド ドロップして矩形の選択範囲を形成します。  
  
    > [!NOTE]
    >  "リボン選択" 操作を使用して、複数のリンクや Functoid を選択できます。 詳細については、[および Functoid を複数のリンクを選択する方法](../core/how-to-select-multiple-links-and-functoids.md)を参照してください。  
  
3.  選択範囲を右クリックします。 クリックして**コピー**します。 または、Ctrl キーを押しながら C キーを押します。  
  
    > [!NOTE]
    >  キーボード ショートカットの一覧は、[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)を参照してください。  
  
4.  選択内容を貼り付ける場所にカーソルを置きます。  
  
5.  グリッド ページを右クリックし、をクリックし、**貼り付け**します。 または、キーボードの Ctrl キーを押しながら V キーを押します。 選択したもののコピーが、新しい場所に表示されます。  
  
### <a name="to-cut-and-paste-a-relationship"></a>リレーションシップを切り取って貼り付けるには  
  
1.  ソリューション エクスプローラーで、BizTalk プロジェクトを開き、マップをダブルクリックして BizTalk マッパーで開きます。  
  
2.  切り取る Functoid やリンクを選択します。  
  
    > [!TIP]
    >  Ctrl キーを押しながら目的の functoid を選択するか、複数のリンクにまたがってマウスをドラッグ アンド ドロップして矩形の選択範囲を形成します。  
  
    > [!NOTE]
    >  "リボン選択" 操作を使用して、複数のリンクや Functoid を選択できます。 詳細については、[および Functoid を複数のリンクを選択する方法](../core/how-to-select-multiple-links-and-functoids.md)を参照してください。  
  
3.  選択範囲を右クリックし、クリックして**切り取り**します。 または、Ctrl キーを押しながら X キーを押します。  
  
    > [!NOTE]
    >  キーボード ショートカットの一覧は、[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)を参照してください。  
  
4.  選択内容を貼り付ける場所にカーソルを置きます。  
  
5.  グリッド ページを右クリックし、をクリックし、**貼り付け**します。 または、キーボードの Ctrl キーを押しながら V キーを押します。 選択したものが既存の場所から削除され、新しい場所に表示されます。