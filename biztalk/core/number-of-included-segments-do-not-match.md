---
title: "含まれているセグメントの数が一致しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c868de02-fda7-4d84-be50-2c08cde0450c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01878c11c8464968b31a7f34ff75b5b494309f90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-included-segments-do-not-match"></a>含まれているセグメントの数が一致しません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12TsIncludedSegCountMismatchDescription|  
|メッセージ テキスト|含まれているセグメントの数が一致しません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、X12 インターチェンジのトランザクション セットのセグメント数が、トランザクション セット トレーラー (SE01 フィールド) の数と等しくないことを示します。 これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジ トレーラーの SE01 フィールドの数が、トランザクション セットのセグメント数と同じであることを確認し、インターチェンジを再送信します。