---
title: 必要な関連アプリケーション名が指定されていません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3e82a39-b052-4702-bfe2-700756a0ee6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c5ecbbcc1a1df97da5339118de873391a5d3ec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268466"
---
# <a name="required-affiliate-application-name-not-specified"></a>必要な関連アプリケーション名が指定されていません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|必要な関連アプリケーション名が指定されていません|  
  
## <a name="explanation"></a>説明  
 **シングル サインオンを使用して**オプションが選択されましたが、関連アプリケーション名が指定されていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 関連アプリケーション名を構成するには、次の手順を実行します。  
  
#### <a name="to-configure-the-affiliate-application-name"></a>関連アプリケーション名を構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**BizTalk アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]** をクリックします。  
  
6.  ポート**型**一覧で、 **Wcf-custom**です。  
  
7.  をクリックして**構成**です。  
  
8.  **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブです。  
  
9. **ユーザー名資格情報**セクションで、値を指定**関連アプリケーション**です。  
  
 SSO 関連アプリケーションの作成の詳細については、次を参照してください[http://go.microsoft.com/fwlink/?LinkId=94347。](http://go.microsoft.com/fwlink/?LinkId=94347)