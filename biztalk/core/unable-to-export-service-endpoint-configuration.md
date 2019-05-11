---
title: サービス エンドポイント構成をエクスポートできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 795145fa-0ce4-498f-a82e-eb752a5f4764
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47c43f08e264b04a8c45fcd8fd946de28d314b81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292779"
---
# <a name="unable-to-export-service-endpoint-configuration"></a>サービス エンドポイント構成をエクスポートできません。
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |              サービス エンドポイント構成をエクスポートすることができません"{0}"              |
  
## <a name="explanation"></a>説明  
 このエラーは、ユーザーは、先に書き込むアクセス許可がないことを示します。 または、必要なプロパティの一部が正しく指定されていないアドレス (URI)、およびバインドの種類など。  
  
## <a name="user-action"></a>ユーザーの操作  
 エンドポイント id を構成するのにには、次の手順を使用します。  
  
#### <a name="to-configure-the-endpoint-identity"></a>エンドポイント id を構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  
  
9. コピー先のフォルダーへの書き込みが許可されていることを確認します。  
  
10. チェック、**動作** タブと**エンドポイント Id**の設定、**全般** タブが有効であることを確認します。  
  
    > [!NOTE]
    >  目的のフォルダーに書き込みアクセス許可が必要です。 これらのアクセス許可を取得する、コンピューターの管理者に問い合わせてください。