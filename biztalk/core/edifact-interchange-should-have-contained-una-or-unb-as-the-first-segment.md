---
title: Edifact インターチェンジに UNA または UNB が最初のセグメントとして含まれていたする必要があります |Microsoft Docs
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
ms.openlocfilehash: 196b589ff886bed005e251c7172a3fd720d88868
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530741"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a>Edifact インターチェンジの必要がありますが含まれている UNA または UNB 最初のセグメントとして
## <a name="details"></a>詳細  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  製品名   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| 製品バージョン |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    イベント ID     |                                                -                                                 |
|  イベント ソース   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI      |
|    コンポーネント    |                                            EDI エンジン                                            |
|  シンボル名  |                                                -                                                 |
|  メッセージ テキスト   | Edifact インターチェンジは、最初のセグメントとして UNA または UNB 含まれていたする必要があります。 代わりに{0}が見つかりました |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI が受信することを示します、最初のセグメントが UNA も UNB セグメントでもないために、パイプラインは受信 EDIFACT インターチェンジを処理できませんでした。 UNA セグメントは省略可能ですが、UNB セグメントは必須です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、インターチェンジの送信者がインターチェンジの最初のセグメントとして UNA または UNB セグメントが含まれていて、インターチェンジを再送信を確認します。