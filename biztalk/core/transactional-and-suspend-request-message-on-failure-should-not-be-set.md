---
title: "トランザクションのオプションが&quot;トランザクション&quot;とエラー処理オプション&quot;エラー発生時に要求メッセージを保留&quot;両方を false に設定する必要があります |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8c47e364fccdb310167e56c6556423c2d4b39d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a>トランザクションのオプションが&quot;トランザクション&quot;とエラー処理オプション&quot;エラー発生時に要求メッセージを保留&quot;両方を false に設定する必要があります
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|メッセージが表示されなくなる可能性があるため、エラー処理オプションの "エラー発生時に場所を無効にする" および "エラー発生時に要求メッセージを保留する" を両方とも false に設定しないでください。 1 つまたは両方のオプションを true に設定してください。|  
  
## <a name="explanation"></a>説明  
 Wcf-netmsmq アダプターで、オプション**トランザクション**と**エラー発生時に要求メッセージを保留**両方を false に設定する必要があります (オフ)。 メッセージ送信の失敗でトランザクションとしてロール バックせずに、メッセージを中断してメッセージ ボックスに保存しない場合は、メッセージが失われることがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 アダプター設定を確認するには、次の手順を実行します。  
  
#### <a name="to-verify-adapter-settings"></a>アダプター設定を確認するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
9. **トランザクション**セクションで、かどうかを**トランザクション**がオンになっています。  
  
10. クリックして、**メッセージ**タブです。  
  
11. かどうかを**エラー発生時に要求メッセージを保留**がオンになっています。  
  
    > [!NOTE]
    >  これらの手順は、場所の受信にのみ適用されます。