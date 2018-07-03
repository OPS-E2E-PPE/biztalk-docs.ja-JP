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
ms.openlocfilehash: 2418517b7695aedd5c80a950a9b74faf5d380346
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973355"
---
# <a name="unable-to-export-service-endpoint-configuration"></a>サービス エンドポイント構成をエクスポートできません
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
 このエラーは、宛先に書き込むアクセス許可がユーザーにない可能性があることを示します。 または、[アドレス (URI)] や [バインディングの種類] など、必要なプロパティの一部が適切に指定されませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 エンドポイント ID を構成するには、次の手順に従います。  
  
#### <a name="to-configure-the-endpoint-identity"></a>エンドポイント ID を構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを特定し、次にトランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. クリックして**構成**します。  
  
8. Wcf **[**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  
  
9. コピー先のフォルダーへの書き込みが許可されていることを確認します。  
  
10. チェック、**動作** タブと**エンドポイント Id**の設定、**全般** タブが有効であることを確認します。  
  
    > [!NOTE]
    >  送信先フォルダーの書き込みアクセス権が必要です。 必要なアクセス権を取得するには、コンピューターの管理者に連絡してください。