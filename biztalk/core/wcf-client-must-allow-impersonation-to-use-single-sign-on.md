---
title: WCF クライアントは、シングル サインオンを使用する権限の借用を許可する必要があります |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5b9f294-4d8a-4a12-91e8-8d325db7c420
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f79cee850fac0689cbf956a966ad0970d36223f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279072"
---
# <a name="wcf-client-must-allow-impersonation-to-use-single-sign-on"></a>WCF クライアントは、シングル サインオンを使用する権限の借用を許可する必要があります。
## <a name="details"></a>詳細  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |           WCF クライアントは、シングル サインオンを使用する偽装を許可する必要があります。            |

## <a name="explanation"></a>説明  
 受信場所のシングル サインオン (SSO) が有効になっているが、WCF クライアントが権限借用を許可していません。  

## <a name="user-action"></a>ユーザーの操作  
 サービスを実行する WCF クライアントが偽装を許可することを確認します。  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、 **Wcf-custom** (または**Wcf-customisolate**)。  

7. をクリックして**構成**です。  

8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブ。  

9. **動作**セクションで、 **ServiceAuthorization**します。 **構成**セクションで、プロパティ**ImpersonateCallerForAllOperations**に設定する必要があります**True**します。  

10. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他**タブ。  

11. 資格情報のセクションでは、オプションを選択します。**使用してシングル サインオン**します。
