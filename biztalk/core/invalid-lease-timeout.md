---
title: 無効なリース タイムアウト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81b7b2a0-e9e6-4165-88bc-f712b5cbacb6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de2eef0627a4297524e0aca62fa9ae64c85e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257354"
---
# <a name="invalid-lease-timeout"></a>リース タイムアウトが無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|リース タイムアウトが無効です。 有効な範囲: 0 ~ 23 時間、0 ~ 59 分、および 0 ~ 59 秒|  
  
## <a name="explanation"></a>説明  
  
## <a name="user-action"></a>ユーザーの操作  
 タイムアウト設定を構成するには、次の手順を実行します。  
  
#### <a name="to-configure-the-timeout-settings"></a>タイムアウト設定を構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]** をクリックします。  
  
6.  ポート**型**一覧で、 **Wcf-nettcp**です。  
  
7.  をクリックして**構成**です。  
  
8.  **Wcf-nettcp トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
9. **接続プール設定**セクションで、確認、**リース タイムアウト (hh:mm:ss)** 範囲が有効です。 使用可能な値は、0 ～ 23 時間、0 ～ 59 分、0 ～ 59 秒です。