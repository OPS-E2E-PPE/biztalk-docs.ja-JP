---
title: エラーの処理エラー |Microsoft ドキュメント
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
ms.openlocfilehash: dafc64afb24ce8bb7995e7852a778b17a556f018
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240826"
---
# <a name="error-handling-errors"></a>エラー処理エラー
診断および WCF エラー処理のエラーを解決するための情報です。  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a>エラー処理オプションの "エラー発生時に場所を無効にする" と "エラー発生時に要求メッセージを保留する" を両方とも false に設定しないでください    
||詳細|  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|エラー処理オプション「エラー発生時に場所を無効にする」および「中断エラー発生時に要求メッセージ」する必要があります両方 false に設定するため、メッセージの損失が発生する可能性があります。 いずれか、または両方のオプションを true に設定してください。|  
  
## <a name="explanation"></a>説明  
 Wcf-netmsmq アダプターで、オプション**エラー発生時に場所を無効にする**と**エラー発生時に要求メッセージを保留**両方を選択する必要があります。 受信場所に無効なメッセージが継続して送信され、メッセージ ボックスに保留および保存されると、メッセージが失われることがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 アダプター設定を構成するには、次の手順を実行します。    

1. 開いている**BizTalk Server 管理**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  選択**プロパティ**です。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  **[構成]** を選択します。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、**メッセージ**タブです。  
  
9. **Error Handling**セクションで、いずれかを確認してください**エラー発生時に場所を無効にする**または**エラー発生時に要求メッセージを保留**がチェックします。