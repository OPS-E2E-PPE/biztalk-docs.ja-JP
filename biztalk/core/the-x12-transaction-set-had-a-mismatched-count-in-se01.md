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
ms.openlocfilehash: 947a557a81c6857b5d31f447acb2ec5a46cfcef9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993355"
---
# <a name="the-x12-transaction-set-had-a-mismatched-count-in-se01"></a>X12 トランザクション セットの SE01 に一致しないカウントがあります
## <a name="details"></a>詳細  
  
|                 |                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                       |
| 製品バージョン |                                  [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                   |
|    イベント ID     |                                                               -                                                               |
|  イベント ソース   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                     |
|    コンポーネント    |                                                          EDI エンジン                                                           |
|  シンボル名  |                                                     X12StSeCountMismatch                                                      |
|  メッセージ テキスト   | X12 トランザクション セットの SE01 に一致しないカウントがあります。 SE01 が{0}されている一方、{1}します。 問題の修正が完了しました。 |
  
## <a name="explanation"></a>説明  
 この警告は、トランザクション セット トレーラー (SE01 フィールド) の数値が、インターチェンジのトランザクション セットのセグメント数と一致しなかったことを示します。 送信パイプラインは、SE01 フィールドのカウントを修正し、警告を表示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 必要なアクションはありません。