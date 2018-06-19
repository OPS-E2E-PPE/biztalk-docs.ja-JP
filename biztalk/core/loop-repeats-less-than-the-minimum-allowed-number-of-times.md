---
title: 小さい値の回数が許容される最小の繰り返しをループ |Microsoft ドキュメント
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
ms.openlocfilehash: 00d9b38712d8b8336daa9357bd20eb34148691b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261986"
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a>ループの繰り返し回数が許容される最小値を下回っています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12SeLoopRepeatsLessTimesDescription|  
|メッセージ テキスト|ループの繰り返し回数が許容される最小値を下回っています|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージのスキーマで規定された最小回数に満たない繰り返し回数を持つループがインターチェンジに含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのループの繰り返し回数がメッセージのスキーマで指定されたループの minOccurs プロパティの回数以上であることを確認し、インターチェンジを再送信します。