---
title: ディス ポジション-通知のオプションが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b807a8-eec9-45a5-83cc-075c91b4bc9e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8956b6ef3dd583522bb142e646920d4731651391
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351004"
---
# <a name="disposition-notification-option-is-invalid"></a>ディス ポジション-通知のオプションが無効です。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |              ディス ポジション-通知-オプションの値:"{0}"が無効です。 {1}              |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 の受信を示す通知オプションが廃棄 - ヘッダーが無効なために、パイプラインは MDN を生成できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 メッセージのディス ポジション-通知オプション ヘッダーが RFC 4130 で説明する構文に準拠しているかどうかを確認"Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2")。 署名済みの受信プロトコル ヘッダーを"optional"または「pcks7-署名」に設定されているの Signed-receipt-micalg ヘッダーが"optional"、"MD5"または"SHA1"に設定されていることを確認します。 (これらのヘッダーの両方に含まれる廃棄通知-オプション ヘッダー。)