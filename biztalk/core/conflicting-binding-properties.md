---
title: "バインドのプロパティの競合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b08c317e-a617-464b-9ee4-007fb41d99b2
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6202385127a676d1f2714b2c3644d135a3d6a7a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="conflicting-binding-properties"></a>バインド プロパティの競合
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|バインドのプロパティの競合: MsmqAuthenticationMode = {0} と MsmqProtectionLevel = \  は有効ではありません。 プロパティのいずれかを変更して、競合を解決してください。|  
  
## <a name="explanation"></a>説明  
 Wcf-netmsmq トランスポートの MSMQ 保護レベル プロパティに設定された**記号**または**EncryptAndSign** None MSMQ 認証モードにします。  
  
## <a name="user-action"></a>ユーザーの操作  
 MSMQ 保護レベルまたは MSMQ 認証モードのプロパティを修正して、MSMQ 保護レベルのプロパティと一致するようにします。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。  
  
9. 値を確認して、MSMQ で**認証モード**一覧および**MSMQ 保護レベル** ボックスの一覧です。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [Wcf-netmsmq 送信ポートを構成する方法](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [Wcf-netmsmq 受信場所を構成する方法](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)