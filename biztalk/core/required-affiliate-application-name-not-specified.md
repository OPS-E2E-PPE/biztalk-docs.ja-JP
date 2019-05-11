---
title: 必要な関連アプリケーション名が指定されていません |Microsoft Docs
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
ms.openlocfilehash: ef35502a6aaec322bc56ed9031cf0045d4bab1e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268012"
---
# <a name="required-affiliate-application-name-not-specified"></a>必要な関連アプリケーション名が指定されていません
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                 必要な関連アプリケーション名が指定されていません                  |
  
## <a name="explanation"></a>説明  
 **シングル サインオンを使用して、** オプションが選択されましたが、関連アプリケーション名が指定されていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 関連アプリケーション名を構成するのにには、次の手順を使用します。  
  
#### <a name="to-configure-the-affiliate-application-name"></a>関連アプリケーション名を構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**BizTalk アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、 **Wcf-custom**します。  
  
7. をクリックして**構成**です。  
  
8. **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブ。  
  
9. **ユーザー名資格情報**セクションの値を指定**関連アプリケーション**します。  
  
   SSO の作成の詳細については、関連アプリケーションを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=94347](http://go.microsoft.com/fwlink/?LinkId=94347)