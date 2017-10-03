---
title: "AS2 デコーダーは MDN の署名しなかったと一致しないため、要求を処理できませんでした |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a42d344-fc28-4bc4-9328-46158f15a008
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc0660a64ff0aeb35976ad1aa45a602d8db0913a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a>MDN の署名が要求と一致しなかったため、AS2 デコーダーの処理は失敗しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|AS2DecoderMdnSigningMismatchFailureDuringProcessing|  
|メッセージ テキスト|MDN の署名が要求と一致しなかったため、AS2 デコーダの処理は失敗しました。  MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:「\ 」MessageID:「\ {2 \}」OriginalMessageID:「\ {3\}」|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、MDN は署名されていたが、署名が要求されていなかったか、または MDN は署名されていなかったが、署名が要求されていたため、受信パイプラインが受信 MDN を処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
1.  MDN に対する署名要求を要求に合わせて変更します。 そのためには、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページを開き、[MDN の要求] プロパティをオンにして、[署名付き MDN を要求する] プロパティをオンまたはオフにします。  
  
2.  元の AS2 メッセージの受信者に連絡し、MDN に署名が必要かどうかについて解決します。