---
title: 最大回数を超えてループが発生します |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ac9f5d3-04ec-4c40-8a1f-17ef0b143cda
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fead7e98c587b78e9614dbc02171f3c19d01934
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380535"
---
# <a name="loop-occurs-over-maximum-times"></a>最大回数を超えてループが発生します
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                        X12LoopOccursOverMaximumTimesDescription                        |
|  メッセージ テキスト   |                            最大回数を超えてループが発生します                             |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジには、メッセージ スキーマで必要な時間の最大数を超える繰り返し回数をループが含まれているためで受信インターチェンジでした、受信パイプラインによって処理することを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、ループが繰り返さインターチェンジでない指定されたメッセージのスキーマのループの maxOccurs プロパティの回数以上とし、インターチェンジを再送信のことを確認します。