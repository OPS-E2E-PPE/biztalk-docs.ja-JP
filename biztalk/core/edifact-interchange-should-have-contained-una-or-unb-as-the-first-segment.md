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
ms.openlocfilehash: 4ee9d5100c8378b5ee411673c4c185dcf5def365
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017836"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a>EDIFACT インターチェンジには、最初のセグメントとして UNA または UNB が含まれている必要があります
## <a name="details"></a>詳細  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  製品名   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| 製品バージョン |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    イベント ID     |                                                -                                                 |
|  イベント ソース   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI      |
|    コンポーネント    |                                            EDI エンジン                                            |
|  シンボル名  |                                                -                                                 |
|  メッセージ テキスト   | EDIFACT インターチェンジには、最初のセグメントとして UNA または UNB が含まれている必要があります。 代わりに{0}が見つかりました |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI が受信することを示します、最初のセグメントが UNA も UNB セグメントでもないために、パイプラインは受信 EDIFACT インターチェンジを処理できませんでした。 UNA セグメントは省略可能ですが、UNB セグメントは必須です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジの最初のセグメントとして UNA または UNB セグメントを含めるよう依頼し、インターチェンジを再送信します。