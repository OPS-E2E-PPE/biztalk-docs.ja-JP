---
title: Edifact トランザクション セットが UNT01 に一致しないカウントが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2859274-78e8-4e16-92b7-c143da6da421
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 428704c78c3d6b615f0272927b03fb57aa66d91b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298789"
---
# <a name="the-edifact-transaction-set-had-a-mismatched-count-in-unt01"></a>UNT01 に一致しないカウントがあります、Edifact トランザクション セット
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| 製品バージョン |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    イベント ID     |                                                                  -                                                                  |
|  イベント ソース   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                        |
|    コンポーネント    |                                                             EDI エンジン                                                              |
|  シンボル名  |                                                      EfactUnhUntCountMismatch                                                       |
|  メッセージ テキスト   | Edifact トランザクション セット UNT01 に一致しないカウントがあります。 UNT01 が{0}されている一方、{1}します。 修正されています。 |
  
## <a name="explanation"></a>説明  
 この警告は、セグメントの数をある UNT01 フィールドが、トランザクション セットのセグメントの数と一致しないことを示します。 UNT01 の値が変更されたか壊れているか、またはセグメントの追加または数が決定された後に削除されました。 送信パイプラインでは、UNT01 フィールドを正しいセグメント数にリセットされ、インターチェンジが送信されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザー操作は必要ありません。