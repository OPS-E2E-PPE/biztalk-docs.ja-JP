---
title: "不明または予期しないバインド要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56021ff3-5abf-46ab-90bb-4531ccc9abd0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c59c20968ea1329a6d689c7976aeba48650fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unknown-or-unexpected-binding-element"></a>不明または予期しないバインド要素が含まれています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|不明または予期しないバインド要素が含まれています|  
  
## <a name="explanation"></a>説明  
 このエラーは、アダプターで、バインディングに指定されているユーザー定義のバインディング要素を検索できないことを示します。 この状況は、主に WCF-Custom アダプターおよび WCF-CustomIsolated アダプターで発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 バインド要素が有効なことを確認するには、次の手順に従います。  
  
#### <a name="to-verify-binding-elements-are-valid"></a>バインディング要素が有効であることを確認するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  Wcf **[***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
9. 構成で指定されたバインド要素が有効なことを確認します。