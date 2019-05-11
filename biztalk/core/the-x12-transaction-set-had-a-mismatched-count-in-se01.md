---
title: X12 トランザクション セットは、SE01 に一致しないカウントが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a90079f5-5939-40b6-9756-d7943240c125
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 762aa7fbbb76cb97e796fa85e89158cd594d8ce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253875"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a>X12 トランザクション セットは、SE01 に一致しないカウントが
## <a name="details"></a>詳細  
  
|                 |                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                       |
| 製品バージョン |                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                   |
|    イベント ID     |                                                               -                                                               |
|  イベント ソース   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                     |
|    コンポーネント    |                                                          EDI エンジン                                                           |
|  シンボル名  |                                                     X12StSeCountMismatch                                                      |
|  メッセージ テキスト   | X12 トランザクション セットは、SE01 に一致しないカウントが。 SE01 が{0}されている一方、{1}します。 修正されています。 |
  
## <a name="explanation"></a>説明  
 この警告は、トランザクション セット トレーラー (SE01 フィールド) 内の数が、インターチェンジのトランザクション セットのセグメントの数と一致しないことを示します。 送信パイプラインは、SE01 フィールドのカウントを修正し、警告を表示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 必要なアクションはありません。