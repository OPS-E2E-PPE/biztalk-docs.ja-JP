---
title: セグメントの繰り返し回数が許容される最小より小さい |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8ca6c3d-f923-49bc-b5d9-65dc2d7adab1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99af818f32d5ca177c60fcccb310f8b9a91f6e2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251041"
---
# <a name="segment-repeats-less-than-the-minimum-allowed-number-of-times"></a>セグメントの繰り返し回数が許容される最小値を下回っています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                        X12SeSegmentRepeatsLessTimesDescription                         |
|  メッセージ テキスト   |             セグメントの繰り返し回数が許容される最小値を下回っています              |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジのセグメントの繰り返しが、ドキュメント スキーマで必要とされる最小回数を下回っているため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に対して、セグメントの繰り返しが少なくともドキュメント スキーマで必要とされる最小回数となるよう依頼し、インターチェンジを再送信してもらいます。