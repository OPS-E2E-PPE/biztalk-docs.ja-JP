---
title: 解析中に発生したエラーです。 Edifact トランザクション セット (グループ) なしのインターチェンジに含まれるは、次のエラーで中断されています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fe401b82d9492590d332dcbdb7d6d59bfaf3c91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348898"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a>解析中に発生したエラーです。 Edifact トランザクション セット (グループ) なしのインターチェンジに含まれるは、次のエラーで中断されています
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| 製品バージョン |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    イベント ID     |                                                                                                           -                                                                                                           |
|  イベント ソース   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                 |
|    コンポーネント    |                                                                                                      EDI エンジン                                                                                                       |
|  シンボル名  |                                                                                      EfactTransactionSetReceiveErrorWithoutGroup                                                                                      |
|  メッセージ テキスト   | 解析中に発生したエラーです。 Edifact トランザクション セット id を持つ '{0}'id (グループ) なしのインターチェンジに含まれる'{1}'、送信者 id'{2}'、受信者 id '{3}' 次のエラーで中断されています。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントを示します、EDI 受信パイプラインでは、識別されたトランザクション、示されたエラーのため、グループなし受信 EDIFACT インターチェンジの解析、インターチェンジの設定時にエラーが発生しました。 トランザクション セットがインターチェンジ内のグループでないことに注意してください。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認します。