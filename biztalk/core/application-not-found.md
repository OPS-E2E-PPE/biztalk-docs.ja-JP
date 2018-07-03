---
title: アプリケーションが見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c37680b2-b38a-40f3-bb27-7b7281299ec3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98499420c773328d647a9c7fa1c80e3ab09ba1b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003459"
---
# <a name="application-not-found"></a>アプリケーションが見つかりません
## <a name="details"></a>詳細  

|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  製品名   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| 製品バージョン |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    イベント ID     |                                                    0                                                    |
|  イベント ソース   |                                                    0                                                    |
|    コンポーネント    |                                                    0                                                    |
|  シンボル名  |                                                    0                                                    |
|  メッセージ テキスト   | アプリケーション"{0}"が見つかりませんでした。アプリケーションが既定の BizTalk 構成データベースに存在することを確認します。 |

## <a name="explanation"></a>説明  
 BizTalk が、BizTalk データベースに存在しないアプリケーションを使用していることを示します。  

## <a name="user-action"></a>ユーザーの操作  
 有効なアプリケーションを構成するには、次の手順を実行します。  

#### <a name="to-configure-a-valid-application"></a>有効なアプリケーションを構成するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションがそこに存在することを確認します。 存在しない場合は、別の有効なアプリケーションを選択します。
