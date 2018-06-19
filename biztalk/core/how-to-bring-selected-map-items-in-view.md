---
title: ビュー内のアイテムを選択したマップを表示する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: b1dff8e981b65b6b91c744ce26648a5f4e06adea
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005547"
---
# <a name="how-to-bring-selected-map-items-in-view"></a>選択したマップ項目をビューに表示する方法
以前のバージョンの BizTalk マッパーでは、マップが大きいスキーマで構成される場合は、送信元スキーマ ウィンドウ、グリッド ページ、およびターゲット スキーマ ウィンドウを手動でスクロールして、関連するすべてのマップ項目を 1 つのビューに収める必要がありました。 BizTalk Server と BizTalk マッパーでは、1 つのビューに、グリッド ページを自動的にスクロールして選択した functoid/リンクのすべての関連するマップ項目を表示することができます。 このトピックでは、この操作を実行する方法について説明します。  
  
 選択内容に応じて (送信元スキーマ ノード、リレーションシップ ビューの要素、またはターゲット スキーマ ノード)、BizTalk マッパーはスキーマ ビューとリレーションシップ ビューを同期して自動的にスクロールし、選択されている項目の全体的なリレーションシップ ビューを表示します。  
  
> [!NOTE]
>  自動スクロール機能は、BizTalk マッパーですべての関連するマップ項目が強調表示されると有効になります。 つまり、最初に選択内容に関連する要素が強調表示され、次に BizTalk マッパーが自動的にスクロールして関連する要素をビューに表示します。  
  
 グリッド オブジェクトが実際に移動されることはありません。 選択を削除または変更すると、グリッド オブジェクトはそれぞれの場所に戻ります。  
  
## <a name="prerequisites"></a>前提条件  
 この操作では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-bring-the-selected-map-items-in-view"></a>選択されているマップ項目をビューに表示するには  
  
1.  マッパー ユーティリティ リボンで自動スクロール アイコンをクリックして![自動 &#45; スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")オフにします。  
  
    > [!NOTE]
    >  ![自動 &#45; スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")アイコンが切り替えられる既定では OFF です。  
  
2.  Functoid またはリンクをクリックします。リレーションシップで関連するマップ項目が強調表示されます。  
  
     次の図では選択されているリンクが青で表示されています。 次に、BizTalk マッパーが選択項目に関連する他のマップ項目を緑色で強調表示します。 図では、選択したリレーションシップのすべての要素が、強調表示されてはいても、現在のビューでは完全には表示されていないことがわかります。  
  
     ![リンク時に自動 &#45; スクロールをオフ](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")  
  
3.  自動スクロール アイコンをクリックして![自動 &#45; スクロール アイコン](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")をオンにします。  
  
     BizTalk マッパーが自動的にスクロールし、選択のすべての関連項目が現在のマップ ビューに表示されます。  
  
     ![自動スクロールをとき表示](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")  
  
    > [!NOTE]
    >  または、Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら U キーを押します。 マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk マッパーの強化された機能の使用](../core/using-enhanced-features-in-biztalk-mapper.md)