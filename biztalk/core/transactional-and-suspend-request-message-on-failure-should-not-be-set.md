---
title: トランザクションのオプション&quot;トランザクション&quot;とエラー処理オプションの&quot;エラー発生時に要求メッセージを保留&quot;両方を false に設定する必要があります |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6c66cc-6713-4396-b0d4-ac6a0e72164f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a194be042fde95d18c80126e53839057d621f46c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279662"
---
# <a name="transactions-option-quottransactionalquot-and-the-error-handling-option-quotsuspend-request-message-on-failurequot-should-not-both-be-set-to-false"></a>トランザクションのオプション&quot;トランザクション&quot;とエラー処理オプションの&quot;エラー発生時に要求メッセージを保留&quot;両方を false に設定する必要があります
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| 製品バージョン |                                                                            [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                            |
|    イベント ID     |                                                                                                        0                                                                                                         |
|  イベント ソース   |                                                                                                        0                                                                                                         |
|    コンポーネント    |                                                                                                        0                                                                                                         |
|  シンボル名  |                                                                                                        0                                                                                                         |
|  メッセージ テキスト   | トランザクションのオプション「トランザクション」およびエラー処理オプション「失敗時に要求メッセージを保留」する必要があります両方では false に設定するため、メッセージの損失が発生する可能性があります。 1 つまたは両方のオプションを true に設定してください。 |
  
## <a name="explanation"></a>説明  
 Wcf-netmsmq アダプターは、オプションで**トランザクション**と**エラー発生時に要求メッセージを保留**両方を false に設定する必要があります (オフ)。 メッセージの損失は、メッセージ送信の失敗はロールバックされません、トランザクションとしてメッセージは中断されませんし、メッセージ ボックスに格納されている場合に発生する可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 アダプター設定を確認するのにには、次の手順を使用します。  
  
#### <a name="to-verify-adapter-settings"></a>アダプター設定を確認するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **Wcf-netmsmq トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。  
  
9. **トランザクション**セクションであるかどうか、**トランザクション**がチェックされます。  
  
10. をクリックして、**メッセージ**タブ。  
  
11. かどうか確認**エラー発生時に要求メッセージを保留**がチェックされます。  
  
    > [!NOTE]
    >  次の手順は、受信場所にのみ適用されます。