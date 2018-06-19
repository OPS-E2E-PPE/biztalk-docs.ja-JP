---
title: データベースまたはサーバー名を取得できませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0590f43b-0aec-491f-bca5-c50ab12552a5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16c694acdc78b704eb6f2578df99239442fd897e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237850"
---
# <a name="could-not-get-the-database-or-the-server-names"></a>データベース名またはサーバー名を取得できませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|データベース名またはサーバー名を取得できませんでした|  
  
## <a name="explanation"></a>説明  
 このエラーは、BizTalk がレジストリから BizTalkMgmtDb 名とサーバー名を読み取れなかったことを示します。 このエラーの考えられる原因の 1 つとして、BizTalk グループが構成されていないことがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のようにして BizTalk グループを構成します。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]] を展開します。  
  
3.  右クリック**BizTalk グループ**です。  
  
4.  **[プロパティ]** をクリックします。  
  
5.  左側のウィンドウでをクリックして**全般**です。  
  
6.  確認、**サーバー**名および**データベース**名が正しい。