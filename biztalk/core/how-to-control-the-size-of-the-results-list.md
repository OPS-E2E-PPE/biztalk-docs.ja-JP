---
title: 結果一覧のサイズを制御する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- results list [Orchestration Debugger], deleting columns
- results list [Orchestration Debugger], limiting list size
- Orchestration Debugger, results list
- results list [Orchestration Designer]
- results list [Orchestration Debugger], adding columns
ms.assetid: 4d41003f-5ea9-4599-8ec0-737c342ffdbd
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80787e4c7dbac57aca9c787943846e924a1a7870
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249738"
---
# <a name="how-to-control-the-size-of-the-results-list"></a>結果一覧のサイズを制御する方法
**グループ ハブ**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、クエリの結果ペインには表示するためにスクロールする必要のある情報の非常に多くの列が含まれています。 ウィンドウの列を追加または削除して、必要な情報だけを表示できます。 列を追加または削除をクリックして、クエリ結果ペインの任意の部分を右クリックして**列の追加/削除**コンテキスト メニューの します。  
  
## <a name="prerequisites"></a>前提条件  
 メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループにこの手順を実行します。  
  
### <a name="to-add-or-remove-columns-in-the-results-list"></a>結果一覧の列を追加または削除するには  
  
1.  任意のセルを右クリックし、**クエリの結果**一覧をクリックして**列の追加/削除**コンテキスト メニューの します。  
  
    > [!NOTE]
    >  右側にある 結果の一覧に既に存在している項目が表示されます**表示列**です。 下にある左側にあるが、結果一覧に存在しないアイテムが表示されます**使用可能な列**です。  
  
2.  列を追加するからの項目のいずれかを選択**使用可能な列** をクリック**追加**その列の一覧に移動する**表示列**です。  
  
3.  列を削除するからの項目のいずれかを選択**表示列** をクリック**削除**その列の一覧に移動する**使用可能な列**です。  
  
 クエリから返される結果の数は、クエリの作成または実行時に、用意されているフィルターを使用して制御できます。  
  
## <a name="columns-in-the-query-results-list"></a>クエリ結果一覧の列  
 クエリの結果は、クエリを開始したビューの下部にある [クエリ結果] ウィンドウに表示されます。 結果一覧に直接アクセスすることはできません。 ショートカット メニューには、現在アクティブなビューで選択されているレコードに対して実行できるすべての操作が表示されます。 たとえば、レコードにサービス インスタンス ID が含まれている場合は、サービス関連の操作が表示されます。 また、メッセージ ID が含まれている場合は、メッセージ関連の操作が表示されます。  
  
 この完全な一覧に含まれている情報がすべて必要であるとは限らないので、表示する列のみを選択したり、削除した列を元に戻したりすることができます。 時間によって、結果一覧を並べ替えると、並べ替えると、インスタンス、ミリ秒単位まで場合でも、(ミリ秒) が一覧に表示されません。 保存されているクエリを再利用した場合、結果には、クエリを実行するたびに選択した列のみが表示されます。  
  
 次の表は、結果一覧に表示される項目の完全な一覧を示します。  
  
|||  
|-|-|  
|**サービスまたはメッセージのフィールド**|**Description**|  
|サービス名|サービス インスタンスの名前。|  
|[イベントの種類]|サービスの種類。たとえば、メッセージング (パイプラインとして報告されます)、オーケストレーション、トランスポート アダプターなどがあります。|  
|[エラーの説明]|エラーが発生した場合、その説明。|  
|状態|クエリを実行したときの操作の状態。|  
|エラー コード|エラーが発生した場合、そのコード。|  
|解読証明書|メッセージまたはサービスに関係する証明書情報が表示されます。|  
|Duration|操作が完了するまでの時間。|  
|ポート名|インスタンスのフローに含まれるポート。|  
|署名|メッセージのデジタル署名情報。|  
|サイズ|メッセージのサイズ (バイト単位)。|  
|Start Time|操作の開始時刻。|  
|[終了時刻]|操作の終了時刻します。|  
|[部分カウント]|メッセージ内のパートの数。|  
|Party|操作を開始したパーティの識別子。|  
|[URI]|開始したパーティの URI。|  
|TimeStamp|操作の開始時刻。|  
|Host|サービス インスタンスを実行している BizTalk ホストの名前。|  
|アセンブリ名|サービス インスタンスを実装する .NET アセンブリの名前です。|  
|アセンブリのバージョン|関連アセンブリのバージョン番号。|  
|展開時刻|サービス インスタンス アセンブリが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に展開された時刻。|  
|アクティビティ ID|一意のサービス インスタンスのアクティビティ (たとえば、同じ ID を持つパイプラインとオーケストレーションによって送信または受信されたメッセージ) を識別します。|  
|[サービス インスタンス ID]|グローバル一意識別子 (GUID) をサービス インスタンスの実行を識別します。|  
|メッセージ インスタンス ID|メッセージ インスタンスを識別するグローバル一意識別子 (GUID)。|  
|サービス ID|サービスを識別するグローバル一意識別子 (GUID)。|  
|[サービス クラス]|クラスの種類 (パイプラインまたはオーケストレーション)。|  
|サービス クラス ID|サービス (オーケストレーションなど) を識別する、サービスに依存しない GUID。|  
|アイコン|結果行のアイコン。|  
|[アダプター]|操作で使用されたアダプター。|