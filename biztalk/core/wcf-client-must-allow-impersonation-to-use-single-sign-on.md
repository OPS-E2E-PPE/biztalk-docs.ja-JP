---
title: WCF クライアントでのシングル サインオンを使用するための偽装を許可する必要があります |Microsoft ドキュメント
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
ms.openlocfilehash: f5e43039a69d057b0d20767ff9061a8d6b4e4f70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288610"
---
# <a name="wcf-client-must-allow-impersonation-to-use-single-sign-on"></a>シングル サインオンを使用するには、WCF クライアントが権限借用を許可する必要があります
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|シングル サインオンを使用するには、WCF クライアントが権限借用を許可する必要があります。|  
  
## <a name="explanation"></a>説明  
 シングル サインオン (SSO) が受信場所で有効ですが、WCF クライアントでは偽装を許可していません。  
  
## <a name="user-action"></a>ユーザーの操作  
 サービスを実行する WCF クライアントが偽装を許可するようにします。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]** をクリックします。  
  
6.  ポート**型**一覧で、 **Wcf-custom** (または**Wcf-customisolate**)。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**動作**タブです。  
  
9. **動作**セクションで、 **ServiceAuthorization**です。 **構成**セクションで、プロパティ**ImpersonateCallerForAllOperations**に設定する必要があります**True**です。  
  
10. **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他** タブ。  
  
11. 資格情報のセクションで、オプションを選択**を使用してシングル サインオン**です。