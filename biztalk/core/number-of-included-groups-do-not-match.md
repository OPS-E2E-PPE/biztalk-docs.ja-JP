---
title: "含まれているグループの数が一致しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d61ac17-92cd-4a5e-81e6-e2c6fc4085bb
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f02262012a5d02cebaf86fae5a4d19d9b5486d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-included-groups-do-not-match"></a>含まれているグループの数が一致しません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidNumberOfIncludedGroupsDescription|  
|メッセージ テキスト|グループ数含まれているが一致しません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジに含まれているグループの数が、インターチェンジ トレーラー (IEA01 フィールド) 内の数と等しくないことを示します。 これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。 (インターチェンジが保存され、トランザクション セットがエラーで中断している場合、またはインターチェンジが分割されている場合、エラー メッセージは通知されません)。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジ トレーラーの IEA01 フィールド内の数が、インターチェンジ内のグループの数と同じであることを確認し、インターチェンジを再送信します。