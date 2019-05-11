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
ms.openlocfilehash: 2e79b28c69786bad3e261cc3269329bd6465a8ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388998"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-signing-did-not-match-our-request"></a>AS2 デコーダーは MDN の署名が、要求と一致しなかったため、処理が失敗しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| 製品バージョン |                                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                       |
|    イベント ID     |                                                                                                   -                                                                                                    |
|  イベント ソース   |                                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                         |
|    コンポーネント    |                                                                                               AS2 エンジン                                                                                               |
|  シンボル名  |                                                                          AS2DecoderMdnSigningMismatchFailureDuringProcessing                                                                           |
|  メッセージ テキスト   | AS2 デコーダー処理は失敗しました、MDN の署名要求が一致しないためです。  MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインが、いずれか、MDN は署名されたが、署名されていないが、署名には、MDN では、または MDN に要求署名されなかったため、要求された MDN の受信 MDN を処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
1.  要求と一致する MDN の署名要求を変更します。 これを行うには、パーティ-AS2 メッセージの受信者 ページ"MDN を要求する"プロパティが選択されていると、AS2 のプロパティ ダイアログ ボックスのいずれかをオンまたはオフ、「要求署名付き MDN を」プロパティを開きます。  
  
2.  Mdn を署名する必要があるかどうかを解決するのには、元の AS2 メッセージの受信者に問い合わせてください。