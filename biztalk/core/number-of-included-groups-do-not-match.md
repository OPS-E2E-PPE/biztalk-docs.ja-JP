---
title: 含まれているグループの数が一致しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d61ac17-92cd-4a5e-81e6-e2c6fc4085bb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b7d64c575f3be0fb3a4d69c56e9509dcb66699b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263448"
---
# <a name="number-of-included-groups-do-not-match"></a>含まれているグループの数が一致しません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                     X12Ta1InvalidNumberOfIncludedGroupsDescription                     |
|  メッセージ テキスト   |                         グループ数に含まれるが一致しません                         |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ内のグループの数が、インターチェンジ トレーラー (IEA01 フィールド) の数と等しくないことを示します。 これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。 (インターチェンジが保存され、トランザクション セットがエラーで中断している場合、またはインターチェンジが分割されている場合、エラー メッセージは通知されません)。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、インターチェンジ トレーラーの IEA01 フィールドの数が、インターチェンジ内のグループの数と同じであるかどうかを確認し、インターチェンジを再送信します。