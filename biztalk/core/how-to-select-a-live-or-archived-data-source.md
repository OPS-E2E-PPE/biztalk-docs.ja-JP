---
title: ライブまたはアーカイブ済みのデータ ソースを選択する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Management database, archived data
- Management database, real-time data
- HAT, real-time data
- archived data, Management database
- HAT, archived data
- real-time data, HAT
- real-time data, Management database
- archived data, HAT
ms.assetid: e2325823-22e1-4a1a-865b-15757b215b29
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7172a822a71e2b0d7dc621e6c1e11b055b723bd3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255290"
---
# <a name="how-to-select-a-live-or-archived-data-source"></a>ライブ データまたはアーカイブ済みのデータのデータ ソースを選択する方法
BizTalktracking では、アーカイブ済みのデータとライブ データの両方にアクセスできます。 メインからライブまたはアーカイブ済みのデータ ソースを選択する**BizTalk Server 管理コンソール**BizTalk Server 管理コンソールのノードです。  既定のソースは、BizTalk 管理サーバーから取得されるライブ データです。 アーカイブ済みのデータを使用する場合は、使用する適切なサーバーとデータベースを選択する必要があります。  
  
-   アーカイブ済みのデータ: アーカイブ済みのデータを分析することができます、ビジネスと、システムの両方の傾向を調べますため、必要なだけさかのぼりすることができます。 アーカイブ済みのデータを選択する場合、そのデータが格納された SQL Server および SQL データベースも選択する必要があります。  
  
     アーカイブ済みのデータを選択して指定**既存の追跡データベースに接続しています.**.  
  
-   ライブ データ: ライブ データの分析を使用するとように監視するオーケストレーションとパイプラインを特定し、開発環境またはステージング環境の問題を修正することができます。 メッセージが保留されている原因など、システムの問題もライブ データを監視することで解決できます。  
  
     選択してライブ データを指定**既存グループへの接続しています.**.  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-select-live-data"></a>ライブ データを選択するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  [メイン] をクリックして**BizTalk Server 管理コンソール**ノード。  
  
3.  をクリックして**既存グループへの接続しています.**  
  
4.  **SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。  
  
5.  **データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**です。  
  
6.  **[OK]** をクリックします。  
  
### <a name="to-select-archived-data"></a>アーカイブ済みのデータを選択するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  [メイン] をクリックして**BizTalk Server 管理コンソール**ノード。  
  
3.  をクリックして**既存の追跡データベースに接続しています.**  
  
4.  **SQL Server 名**ボックスに、BizTalk 管理データベースをホストするサーバーの名前を入力します。  
  
5.  **データベース名**ドロップダウン リスト ボックスで、 **BizTalkMgmtDb**です。  
  
6.  **[OK]** をクリックします。