---
title: AS2 デコーダーは、MDN が失敗したメッセージの AS2 処理によって示されたため失敗しました |Microsoft Docs
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
ms.openlocfilehash: 3c2507c1eafa258335302f4670f612db1b213e82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389016"
---
# <a name="the-as2-decoder-failed-processing-because-the-mdn-indicated-the-as2-message-failed-processing"></a>AS2 デコーダーは MDN に失敗したメッセージの AS2 処理が示されるため、処理できませんでした。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                |
| 製品バージョン |                                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                            |
|    イベント ID     |                                                                                                        -                                                                                                         |
|  イベント ソース   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                              |
|    コンポーネント    |                                                                                                    AS2 エンジン                                                                                                    |
|  シンボル名  |                                                                                      AS2DecoderMdnProcessingFailureReturned                                                                                      |
|  メッセージ テキスト   | AS2 デコーダー、MDN が AS2 メッセージを示すため、処理されているエラー処理に失敗しました。  MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントでは、元の AS2 メッセージの受信者が元の AS2 メッセージを処理できなかったことを MDN 応答が表示されることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決する、AS2 メッセージの受信者にお問い合わせください、受信側では、処理が失敗した理由を判断し、元の AS2 メッセージを修正し再送信します。