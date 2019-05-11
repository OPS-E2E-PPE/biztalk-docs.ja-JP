---
title: エラーのエラー処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 602be8a5-1f28-457d-8e12-ba06cff65491
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02203fcdde41ff078e3fcd9a5e71516f11599732
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388834"
---
# <a name="error-handling-errors"></a>エラー処理エラー
診断および WCF エラー処理のエラーを解決するための情報です。  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a>エラー処理オプションの "エラー発生時に場所を無効にする" と "エラー発生時に要求メッセージを保留する" を両方とも false に設定しないでください    

|                 |                                                                                                詳細                                                                                                 |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| 製品バージョン |                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                       |
|    イベント ID     |                                                                                                   0                                                                                                    |
|  イベント ソース   |                                                                                                   0                                                                                                    |
|    コンポーネント    |                                                                                                   0                                                                                                    |
|  シンボル名  |                                                                                                   0                                                                                                    |
|  メッセージ テキスト   | エラーの処理オプション「エラー発生時の場所を無効にする」および「中断要求メッセージをエラー」が両方では false に設定するため、メッセージの損失が発生すます。 1 つまたは両方のオプションを true に設定してください。 |

## <a name="explanation"></a>説明  
 Wcf-netmsmq アダプターは、オプションで**エラー上の場所を無効にする**と**エラー発生時に要求メッセージを保留**両方を選択する必要があります。 これらのメッセージが中断され、メッセージ ボックスに格納されているないときに、無効なメッセージを受信する受信場所では、メッセージの損失が発生します。  

## <a name="user-action"></a>ユーザーの操作  
 アダプター設定を構成するのにには、次の手順を使用します。    

1. 開いている**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. 選択**プロパティ**します。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. **[構成]** を選択します。  

8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、**メッセージ**タブ。  

9. **エラー処理**セクションで、いずれかを確認します**エラー上の場所を無効にする**または**エラー発生時に要求メッセージを保留**がチェックされます。
