---
title: エラー メッセージを一覧表示、検索、および並べ替え |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 850b9682-8eba-4a3f-8508-d3eefcd715b7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c68d5411bc7f9837a1e1f41892b2741d0b56a3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261501"
---
# <a name="listing-searching-and-sorting-fault-messages"></a>エラー メッセージを一覧表示、検索、および並べ替え
ESB 管理ポータルのホーム ページを使用すると、Microsoft BizTalk Server 内で実行するアプリケーションの状態の全体像を取得します。 エラー ページを使用できるさまざまな条件に基づいて、エラー メッセージを照会します。  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a>現在の BizTalk Server アプリケーションの状態の概要を表示するには  
  
1.  開く、[ポータル ホーム ページ](../esb-toolkit/portal-home-page.md)します。 このページには、アプリケーション全体の状態、エラーの概要、Universal Description, Discovery, and Integration (UDDI) の登録、およびエラーの種類とアプリケーションの内訳を表示するグラフの最近の要求が表示されます。  
  
2.  情報を表示するアプリケーションを選択する をクリックして、**アプリケーションの選択**最初のグラフの上にリンクし選択するか表示されるインストール済みの BizTalk Server アプリケーションの一覧でチェック ボックスをオフにします。  
  
3.  ポータルが情報を表示する期間を変更するには、次のように選択します。**時間、日、週、月、四半期、年、** または**すべて**最初のグラフの上のドロップダウン リストでします。  
  
4.  アプリケーションと、表示期間の一覧については、ホーム ページで使用する既定の設定を変更するで設定を編集、[ポータル個人用設定ページ](../esb-toolkit/portal-my-settings-page.md)します。  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a>表示するには、検索および並べ替えエラー ESB 管理ポータルでメッセージ  
  
1.  開く、[設定 ページの障害](../esb-toolkit/fault-settings-page.md)します。 このページでは、各エラーのプロパティの切り詰められた一覧を表示し、さまざまな条件でエラーの分析をサポートします。  
  
2.  ページに表示されるエラーの一覧をフィルター処理するには、エラーの一覧の上のテキスト ボックス、ドロップダウン リストを使用します。 アプリケーション、期間、エラー コード番号、エラー カテゴリの名前、エラーの種類のテキスト、および最小値/最大エラーの重大度によって表示される行をフィルター処理することができます。 空のままに、コントロールのいずれかのこの条件には、その値に関係なくすべてのメッセージを取得します。  
  
3.  クリックして**フィルターの適用**一致エラーの一覧を表示します。 非常に大きな障害のデータベースでフィルター処理が結果を表示するには数秒間かかる場合がありますに注意してください。  
  
4.  適切な値を選択 ページで、またはより少ない行を表示するには**1 ページあたりのレコード**ドロップダウン リスト。  
  
5.  エラー メッセージの一覧を並べ替えるには、列見出しをクリックします。 行を逆の順序で並べ替えるには、同じ列の見出しをもう一度をクリックします。  
  
6.  クリックして**Excel にエクスポート**を Microsoft Excel で表示できる形式でエラー メッセージの完全な一覧をダウンロードします。