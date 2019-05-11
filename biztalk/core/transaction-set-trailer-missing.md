---
title: トランザクション セットのトレーラーがありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07753300-fe47-47a6-a947-6abec10c1c90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f75851b8c2b781d943611657e016775c8bce95b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279742"
---
# <a name="transaction-set-trailer-missing"></a>トランザクション セットのトレーラーがありません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                             X12TsTrailerMissingDescription                             |
|  メッセージ テキスト   |                            トランザクション セットのトレーラーがありません                             |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セットに SE トランザクション セット トレーラー (X12 トランザクション セットの場合) または UNT メッセージ トレーラー (EDIFACT トランザクション セットの場合) が含まれていなかったため、受信パイプラインで受信トランザクション セットを処理できなかったか、送信パイプラインで送信トランザクション セットを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、トランザクション セットに SE トランザクション セット トレーラー (X12 トランザクション セットの場合) または UNT メッセージ トレーラー (EDIFACT トランザクション セットの場合) を追加することをトランザクション セットの送信元に依頼します。