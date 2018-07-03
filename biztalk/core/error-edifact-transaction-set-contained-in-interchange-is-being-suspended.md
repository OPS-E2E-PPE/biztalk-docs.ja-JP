---
title: 解析中にエラーが発生しました。 Edifact トランザクション セット (グループ) なしのインターチェンジに含まれるは、次のエラーで中断されています |Microsoft Docs
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
ms.openlocfilehash: c2e0d8e2b03decf2db806a08f082b7aace276a8e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006419"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a>解析中にエラーが発生しました。 インターチェンジに含まれる EDIFACT トランザクション セット (グループ以外) が、次のエラーで中断されています
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                   |
| 製品バージョン |                                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                               |
|    イベント ID     |                                                                                                           -                                                                                                           |
|  イベント ソース   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                 |
|    コンポーネント    |                                                                                                      EDI エンジン                                                                                                       |
|  シンボル名  |                                                                                      EfactTransactionSetReceiveErrorWithoutGroup                                                                                      |
|  メッセージ テキスト   | 解析中にエラーが発生しました。 Edifact トランザクション セット id を持つ '{0}'id (グループ) なしのインターチェンジに含まれる'{1}'、送信者 id'{2}'、受信者 id '{3}' 次のエラーで中断されています。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジで識別されたトランザクション セットで、示されたエラーが発生したため、受信 EDIFACT インターチェンジ (グループ以外) の解析時に EDI 受信パイプラインでエラーが発生したことを示します。 このトランザクション セットは、インターチェンジ内のグループには含まれないことに注意してください。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。