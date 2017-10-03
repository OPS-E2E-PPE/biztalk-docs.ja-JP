---
title: "クライアント エンドポイント構成をエクスポートできません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d93fe5e-fdb2-49c5-86de-d428b1ecda7f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 941d42ff01bcf578bd7ba7c426c6fe5ca2bfbce3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-export-client-endpoint-configuration"></a>クライアント エンドポイント構成をエクスポートできません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|クライアント エンドポイント構成を "{0}" にエクスポートできません|  
  
## <a name="explanation"></a>説明  
 このエラーは、以下のいずれかを示します。  
  
-   宛先に書き込むアクセス許可がユーザーにない可能性があります。  
  
     \- または -  
  
-   一部の必須プロパティが正しく指定されていませんなど**アドレス (URI)**と**バインディングの種類**です。  
  
## <a name="user-action"></a>ユーザーの操作  
 次の手順を使用して、ユーザーのアクセス許可を確認し、確認を**アドレス (URI)**と**バインディングの種類**設定が有効です。  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a>ユーザーのアクセス許可と設定を確認するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、トランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  Wcf **[***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
9. 宛先フォルダーへの書き込みが許可されていることを確認します。  
  
10. チェック、**動作** タブおよび**エンドポイント Id**で設定**全般**が有効であることを確認するには、タブ。  
  
> [!NOTE]
>  送信先フォルダーの書き込みアクセス権が必要です。 必要なアクセス権を取得するには、コンピューターの管理者に連絡してください。