---
title: 見つかったデータ要素数が少なすぎます |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6eca6c1-73ee-4b9a-be84-461051eda963
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8244f927cb7aff9cd0cb517dd132b986d53d67f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278962"
---
# <a name="too-few-data-elements-found"></a>見つかったデータ要素が少なすぎます
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12FeTooFewDataElementsFoundDescription|  
|メッセージ テキスト|見つかったデータ要素が少なすぎます|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジのセグメントに含まれていたデータ要素の数が、ドキュメント スキーマまたはサービス スキーマで要求されている数を下回っていたため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に対して、セグメントに必要な数のデータ要素を含めるよう依頼し、インターチェンジを再送信します。