---
title: クライアント エンドポイント構成をエクスポートできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d93fe5e-fdb2-49c5-86de-d428b1ecda7f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ce781105c96f12705605e7c97f0e5229d2017f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292795"
---
# <a name="unable-to-export-client-endpoint-configuration"></a>クライアント エンドポイント構成をエクスポートできません。
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |              クライアント エンドポイント構成をエクスポートできません"{0}"               |
  
## <a name="explanation"></a>説明  
 このエラーは、次のいずれかを示します。  
  
-   ユーザーは、先に書き込むアクセス許可がありません。  
  
     \- または -  
  
-   必要なプロパティの一部が正しく指定されていないなど**アドレス (URI)** と**バインドの種類**します。  
  
## <a name="user-action"></a>ユーザーの操作  
 次の手順を使用して、ユーザーのアクセス許可の確認入力と確認を**アドレス (URI)** と**バインドの種類**設定が無効です。  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a>ユーザーのアクセス許可を確認し、設定を確認するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを特定して、トランスポートを見つけます。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  
  
9. コピー先のフォルダーへの書き込みが許可されていることを確認します。  
  
10. チェック、**動作** タブと**エンドポイント Id**設定**全般**が有効であることを確認するには、タブ。  
  
> [!NOTE]
>  目的のフォルダーに書き込みアクセス許可が必要です。 これらのアクセス許可を取得する、コンピューターの管理者に問い合わせてください。