---
title: AS2 デコーダーは MDN の署名が、要求と一致しなかったため、処理が失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a42d344-fc28-4bc4-9328-46158f15a008
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a4d5cb5cd1825f5620ab39e4c770eb9818a5ade
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978876"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a>MDN の署名が要求と一致しなかったため、AS2 デコーダーの処理は失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| 製品バージョン |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    イベント ID     |                                                                                                   -                                                                                                    |
|  イベント ソース   |                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                         |
|    コンポーネント    |                                                                                               AS2 エンジン                                                                                               |
|  シンボル名  |                                                                          AS2DecoderMdnSigningMismatchFailureDuringProcessing                                                                           |
|  メッセージ テキスト   | MDN の署名が要求と一致しなかったため、AS2 デコーダの処理は失敗しました。  MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、MDN は署名されていたが、署名が要求されていなかったか、または MDN は署名されていなかったが、署名が要求されていたため、受信パイプラインが受信 MDN を処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
1.  MDN に対する署名要求を要求に合わせて変更します。 そのためには、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページを開き、[MDN の要求] プロパティをオンにして、[署名付き MDN を要求する] プロパティをオンまたはオフにします。  
  
2.  元の AS2 メッセージの受信者に連絡し、MDN に署名が必要かどうかについて解決します。