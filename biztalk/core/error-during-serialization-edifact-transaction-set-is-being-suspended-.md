---
title: Edifact トランザクション セットがインターチェンジのエラーに含まれている |Microsoft ドキュメント
description: シリアル化中にエラーが発生しました。 インターチェンジに含まれる EDIFACT トランザクション セット (グループ以外) が、次のエラーで中断されています
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a0a33ac-d83e-495c-ba75-88c15ad7cfcd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f089e49941ffec7d3392b3bc35edcbc4eefec5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241474"
---
# <a name="edifact-transaction-set-is-suspended-error-and-details"></a>Edifact トランザクション セットは、中断されたエラーの詳細

`Error encountered during serialization. The Edifact transaction set contained in interchange (without group) is being suspended with following errors`

## <a name="details"></a>詳細  
  
|||  
|---|---|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactTransactionSetSendErrorWithoutGroup|  
|メッセージ テキスト|シリアル化中にエラーが発生しました。 Edifact トランザクション セット id '{0}' id '{1}'、送信者 id '{2}' を持つ (グループなしの) インターチェンジに含まれている受信者 id '{3}' で中断されていますが次のエラー。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別されたトランザクション セットに、示されたエラーがあったため、EDIFACT の送信インターチェンジのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。 このトランザクション セットは、インターチェンジ内のグループには含まれないことに注意してください。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、情報を使用して、エラー メッセージに、トランザクション セットでエラーを特定し、問題の解決方法を決定します。