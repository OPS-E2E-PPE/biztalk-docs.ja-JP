---
title: Edifact トランザクション セットに含まれるインターチェンジ エラー |Microsoft Docs
description: シリアル化中に発生したエラーです。 Edifact トランザクション セット (グループ) なしのインターチェンジに含まれるは、次のエラーで中断されています
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 368b5ad0f26b642d4d7f3575a8c7a03abac4ca0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389200"
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a>Edifact トランザクション セットが中断されたエラーと詳細

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                      |
| 製品バージョン |                                                                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                  |
|    イベント ID     |                                                                                                              -                                                                                                               |
|  イベント ソース   |                                                                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                    |
|    コンポーネント    |                                                                                                          EDI エンジン                                                                                                          |
|  シンボル名  |                                                                                           EfactTransactionSetSendErrorWithoutGroup                                                                                           |
|  メッセージ テキスト   | シリアル化中に発生したエラーです。 Edifact トランザクション セット id を持つ '{0}'id (グループ) なしのインターチェンジに含まれる'{1}'、送信者 id'{2}'、受信者 id '{3}' 次のエラーで中断されています。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI 送信パイプラインでは、識別されたトランザクション セット、示されたエラーのため送信 EDIFACT インターチェンジをシリアル化するときに、エラーが発生したことを示します。 トランザクション セットがインターチェンジ内のグループでないことに注意してください。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、問題の解決方法を確認します。