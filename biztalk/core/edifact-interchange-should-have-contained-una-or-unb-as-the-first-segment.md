---
title: Edifact インターチェンジに UNA または UNB の最初のセグメントとして含まれていた必要があります |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673df728dea00852e9713aed12f8ced902a4fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240034"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a>EDIFACT インターチェンジには、最初のセグメントとして UNA または UNB が含まれている必要があります
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|EDIFACT インターチェンジには、最初のセグメントとして UNA または UNB が含まれている必要があります。 代わりに、{0} が見つかりました。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI 受信を示す最初のセグメントが UNA も UNB セグメントでもないために、パイプラインは受信 EDIFACT インターチェンジを処理できませんでした。 UNA セグメントは省略可能ですが、UNB セグメントは必須です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジの最初のセグメントとして UNA または UNB セグメントを含めるよう依頼し、インターチェンジを再送信します。