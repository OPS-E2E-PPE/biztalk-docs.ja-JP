---
title: ビュー内のアイテムを選択したマップを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e287b22-5738-428a-aa35-cced877e51ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd4a932b00ac2d0a89eb9cfb8f343fd9ab0d4fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342618"
---
# <a name="how-to-bring-selected-map-items-in-view"></a>選択したマップ項目をビューに表示する方法
以前のバージョンの BizTalk マッパーでは、マップが大きいスキーマで構成される場合必要がある元スキーマ ペイン、グリッド ページで、および 1 つのビューに関連するマップのすべての項目をターゲット スキーマ ウィンドウを手動でスクロールします。 BizTalk Server と BizTalk マッパーを使用すると、グリッド ページを自動的にスクロールして、選択した functoid/リンクのすべての関連するマップ項目を 1 つのビューに取り込むことができます。 このトピックでは、操作を実行する方法について説明します。  
  
 (送信元スキーマのノード、リレーションシップ ビュー、またはターゲット スキーマのノード内の要素) 選択内容に応じて、BizTalk マッパーはスキーマ ビューと同期的に、リレーションシップ ビューが自動的にスクロールとの関係の全体的なビューが表示されます、選択された項目。  
  
> [!NOTE]
>  自動スクロール機能は、BizTalk マッパーには、すべての関連するマップ項目が強調表示される後効果に渡されます。 つまり、最初の選択項目に関連する要素が強調表示されとし、BizTalk マッパーが自動的にスクロールに関連する要素の表示にします。  
  
 BizTalk マッパーは、grid オブジェクトを実際には移動しません。 Grid オブジェクトは、削除、または選択範囲を変更するときにそれぞれの場所に戻ります。  
  
## <a name="prerequisites"></a>前提条件  
 この操作では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-bring-the-selected-map-items-in-view"></a>ビューに、選択したマップ項目を表示するには  
  
1.  マッパー ユーティリティ リボンで自動スクロール アイコンをクリックします。![自動&#45;スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")してオフにします。  
  
    > [!NOTE]
    >  ![自動&#45;スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")アイコンが切り替えられた既定でオフです。  
  
2.  Functoid またはリンクをクリックします。リレーションシップに関連するマップ項目が強調表示されます。  
  
     次の図では、青の色の選択したリンクが表示されます。 さらに、BizTalk マッパーでは、緑の色の選択内容に関連するその他のマップ項目が強調表示します。 図で、現在のビューで完全にできないの強調表示されますが、選択したリレーションシップのすべての要素がわかります。  
  
     ![リンクするときに自動&#45;スクロール](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")  
  
3.  自動スクロール アイコンをクリックします。![自動&#45;スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")オンにします。  
  
     BizTalk マッパーは、選択範囲を現在のマップ ビューに関連するすべての項目を自動的にスクロールします。  
  
     ![自動スクロールはオンになっているときに表示](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")  
  
    > [!NOTE]
    >  または、CTRL + M, CTRL + U、キーボードからキーを押すことができます。 マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能の使用](../core/using-enhanced-features-in-biztalk-mapper.md)