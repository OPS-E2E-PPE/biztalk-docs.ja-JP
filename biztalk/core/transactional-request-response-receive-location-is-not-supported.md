---
title: トランザクションの要求-応答の受信場所はサポートされていません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c89b619-280c-4ab5-b6aa-06b14a075f8e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34de32b338a78b598941d4e828c1a0b736dde4e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278514"
---
# <a name="transactional-request-response-receive-location-is-not-supported"></a>トランザクションの要求 - 応答の受信場所がサポートされていません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|トランザクションの要求-応答の受信場所がサポートされていません。|  
  
## <a name="explanation"></a>説明  
 このエラーは、WCF の要求-応答の受信場所について有効になるようにトランザクションが設定されたことを示します。 要求-応答の受信場所はメッセージ ボックス データベースのため、BizTalk ではトランザクションはサポートされていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 標準の WCF アダプターの場合、要求-応答の受信場所を構成するコードを開きます。 いることを確認、 **EnableTransaction**用の XML データ内の要素、 **TransportTypeData**のプロパティ、 **ITransportInfo**に設定されているインターフェイス**False**.  
  
 WCF-Custom アダプターの場合  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]** をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
9. TransactionFlow プロパティに設定されていることを確認**False**です。