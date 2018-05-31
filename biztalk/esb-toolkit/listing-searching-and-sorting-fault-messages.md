---
title: 一覧表示、検索、および並べ替えのエラー メッセージ |Microsoft ドキュメント
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
ms.openlocfilehash: 768dd7f51ff09bad76115f8a7e2a95a11ce47981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294642"
---
# <a name="listing-searching-and-sorting-fault-messages"></a>一覧表示、検索、および並べ替えのエラー メッセージ
ESB の管理ポータルのホーム ページを使用すると、Microsoft BizTalk Server 内で実行されているアプリケーションの状態の全体的なビューを提供します。 エラー ページを使用できるさまざまな条件に基づいて、エラー メッセージをクエリします。  
  
### <a name="to-see-an-overview-of-the-status-of-current-biztalk-server-applications"></a>現在の BizTalk Server アプリケーションの状態の概要を表示するには  
  
1.  開く、[ポータルのホーム ページ](../esb-toolkit/portal-home-page.md)です。 このページには、アプリケーション全体の状態、エラーの概要、Universal Description, Discovery, and Integration (UDDI) の登録、およびエラーとアプリケーションの種類によっての内訳を表示するグラフの最近の要求が表示されます。  
  
2.  情報を表示するアプリケーションを選択するをクリックして、**アプリケーションの選択**最初のグラフの上にリンクし、選択するか表示されるインストール済みの BizTalk Server アプリケーションの一覧にあるチェック ボックスをオフにします。  
  
3.  ポータルが情報を表示する期間を変更するには、次のように選択します。**時間、日、週、月、四半期、年、** または**すべて**最初のグラフ上のドロップダウン リストでします。  
  
4.  アプリケーションと、表示期間の一覧で、ホーム ページに使用する既定の設定を変更するで設定を編集、[ポータルの [設定] ページ](../esb-toolkit/portal-my-settings-page.md)です。  
  
### <a name="to-list-search-for-and-sort-fault-messages-in-the-esb-management-portal"></a>この一覧を表示すると、検索、および並べ替えエラー ESB の管理ポータルでメッセージ  
  
1.  開く、[設定 ページをフォールト](../esb-toolkit/fault-settings-page.md)です。 このページは、各エラーのプロパティの切り詰められた一覧を表示し、さまざまな条件でエラーの分析をサポートします。  
  
2.  ページに表示されるエラーの一覧をフィルター処理するには、エラーの一覧の上のテキスト ボックス、ドロップダウン リストを使用します。 アプリケーション、期間、エラー コード番号、エラー カテゴリの名前、エラーの種類のテキスト、最小値/最大エラーの重大度で表示される行をフィルター処理することができます。 空のままにするコントロールのいずれかのこの条件には、その値に関係なくすべてのメッセージを取得します。  
  
3.  をクリックして**フィルターの適用**一致するエラーの一覧を表示します。 非常に大きな障害データベースでフィルター処理がの結果を表示するのには数秒間かかる場合がありますに注意してください。  
  
4.  適切な値の選択ページで、またはより少ない行を表示するには**1 ページあたりのレコード**ドロップダウン リスト。  
  
5.  エラー メッセージの一覧を並べ替えるには、列見出しをクリックします。 行を逆順に並べ替えるには、するには、同じ列の見出しをもう一度をクリックします。  
  
6.  をクリックして**Excel にエクスポート**Microsoft Excel で表示できる形式でのエラー メッセージの完全な一覧をダウンロードします。