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
ms.openlocfilehash: c494614465df4faeead9ec30d79dfdf47cc321c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999083"
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
|  メッセージ テキスト   | エラーの処理オプション「エラー発生時の場所を無効にする」および「中断要求メッセージをエラー」が両方では false に設定するため、メッセージの損失が発生すます。 いずれか、または両方のオプションを true に設定してください。 |

## <a name="explanation"></a>説明  
 Wcf-netmsmq アダプターは、オプションで**エラー上の場所を無効にする**と**エラー発生時に要求メッセージを保留**両方を選択する必要があります。 受信場所に無効なメッセージが継続して送信され、メッセージ ボックスに保留および保存されると、メッセージが失われることがあります。  

## <a name="user-action"></a>ユーザーの操作  
 アダプター設定を構成するには、次の手順を実行します。    

1. 開いている**BizTalk Server 管理**します。  

2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを特定し、次にトランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. 選択**プロパティ**します。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. **[構成]** を選択します。  

8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、**メッセージ**タブ。  

9. **エラー処理**セクションで、いずれかを確認します**エラー上の場所を無効にする**または**エラー発生時に要求メッセージを保留**がチェックされます。
