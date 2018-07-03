---
title: バインドのプロパティの競合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b08c317e-a617-464b-9ee4-007fb41d99b2
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 271b9efa9d30d5c315bfd6061bfbf011289ea620
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012083"
---
# <a name="conflicting-binding-properties"></a>バインド プロパティの競合
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                    |
| 製品バージョン |                                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                |
|    イベント ID     |                                                                            0                                                                            |
|  イベント ソース   |                                                                            0                                                                            |
|    コンポーネント    |                                                                            0                                                                            |
|  シンボル名  |                                                                            0                                                                            |
|  メッセージ テキスト   | バインドのプロパティの競合: MsmqAuthenticationMode ={0}と MsmqProtectionLevel ={1}が無効です。 プロパティのいずれかを変更して、競合を解決してください。 |
  
## <a name="explanation"></a>説明  
 Wcf-netmsmq トランスポートの MSMQ 保護レベル プロパティに設定されました**サインオン**または**EncryptAndSign** None MSMQ 認証モード。  
  
## <a name="user-action"></a>ユーザーの操作  
 MSMQ 保護レベルまたは MSMQ 認証モードのプロパティを修正して、MSMQ 保護レベルのプロパティと一致するようにします。  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを特定し、次にトランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. クリックして**構成**します。  
  
8. **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。  
  
9. MSMQ の値をチェック**認証モード**一覧と**MSMQ 保護レベル**一覧。  
  
   詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [Wcf-netmsmq 送信ポートを構成する方法](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [Wcf-netmsmq 受信場所を構成する方法](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)