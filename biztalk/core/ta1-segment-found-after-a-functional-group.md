---
title: TA1 セグメントの機能グループの後に見つかった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3d090a-0916-4a0e-82dc-2c9af9f97683
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4526c07171a96904299c60f12ee5c34c01816a42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291674"
---
# <a name="ta1-segment-found-after-a-functional-group"></a>TA1 セグメントの機能グループの後に見つかりました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                              TA1FoundAfterFunctionalGroup                              |
|  メッセージ テキスト   |     機能グループの後に TA1 セグメントが見つかったため、 メッセージは拒否されています      |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信確認に機能グループに続いて TA1 セグメントが含まれていたため、受信パイプラインで受信確認を処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、TA1 受信確認の送信者に対して、インターチェンジで TA1 セグメントの前に機能グループが含まれていないことを確認するよう依頼し、受信確認を再送信します。