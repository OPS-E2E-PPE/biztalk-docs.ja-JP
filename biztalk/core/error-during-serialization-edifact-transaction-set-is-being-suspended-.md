---
title: Edifact トランザクション セットに含まれるインターチェンジ エラー |Microsoft Docs
description: シリアル化中にエラーが発生しました。 インターチェンジに含まれる EDIFACT トランザクション セット (グループ以外) が、次のエラーで中断されています
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
ms.openlocfilehash: e5fcd7702ce791037d8a7320f647955fca1c9489
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981931"
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
|  メッセージ テキスト   | シリアル化中にエラーが発生しました。 Edifact トランザクション セット id を持つ '{0}'id (グループ) なしのインターチェンジに含まれる'{1}'、送信者 id'{2}'、受信者 id '{3}' 次のエラーで中断されています。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別されたトランザクション セットに、示されたエラーがあったため、EDIFACT の送信インターチェンジのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。 このトランザクション セットは、インターチェンジ内のグループには含まれないことに注意してください。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、問題の解決方法を確認します。