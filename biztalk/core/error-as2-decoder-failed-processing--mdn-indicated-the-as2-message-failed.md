---
title: AS2 デコーダーは MDN には、失敗したメッセージの AS2 処理が示されているために、処理が失敗しました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bce620a-f336-435e-b7c3-3db060f2819d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20454f1c551b6b4828c42e09f0442b83275256ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240122"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a>AS2 メッセージを処理できなかったことが MDN によって示されたため、AS2 デコーダーの処理は失敗しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|AS2DecoderMdnProcessingFailureReturned|  
|メッセージ テキスト|AS2 メッセージを処理できなかったことが MDN によって示されたため、AS2 デコーダの処理は失敗しました。  MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:「\ 」MessageID:「\ {2 \}」OriginalMessageID:「\ {3\}」|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 メッセージの受信者が元の AS2 メッセージを処理できなかったことが MDN 応答に示されていることを表します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 メッセージの受信者に連絡し、受信側での処理が失敗した理由を確認して、元の AS2 メッセージを修正して再送信します。