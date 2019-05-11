---
title: AS2 デコーダーの処理中に例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5f16d2e-e83c-4e2c-84be-41b5ed012dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3635a824fbd551daa265d3448434430eba252867
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299062"
---
# <a name="the-as2-decoder-encountered-an-exception-during-processing"></a>AS2 デコーダーの処理中に例外が発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                         |
| 製品バージョン |                                                                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                     |
|    イベント ID     |                                                                                                 -                                                                                                 |
|  イベント ソース   |                                                      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                       |
|    コンポーネント    |                                                                                            AS2 エンジン                                                                                             |
|  シンボル名  |                                                                          AS2DecoderExceptionEncounteredDuringProcessing                                                                           |
|  メッセージ テキスト   | AS2 デコーダーでは、処理中に例外が発生しました。  メッセージと例外の詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"MessageType:"{3}"例外:"{4}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 デコーダー問題のための受信 AS2 メッセージを受信パイプラインが処理しないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 エラー コードをチェックしてエラー状態の性質を決定します。 AS2 エラー コードの詳細については、トピックでは、「AS2 エラー コード」を参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ ファイル。