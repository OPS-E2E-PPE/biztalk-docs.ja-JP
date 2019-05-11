---
title: 未満の最小回数の許容回数をループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0be21d1d-86da-456b-83e6-c91f1dc9fb48
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27188ecbf45cb147d718a7349c123ce195c4a1a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380499"
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a>ループの繰り返し回数が許容される最小値を下回っています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                          X12SeLoopRepeatsLessTimesDescription                          |
|  メッセージ テキスト   |               ループの繰り返し回数が許容される最小値を下回っています               |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージのスキーマで規定された最小回数に満たない繰り返し回数を持つループがインターチェンジに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのループの繰り返し回数がメッセージのスキーマで指定されたループの minOccurs プロパティの回数以上であることを確認し、インターチェンジを再送信します。