---
title: 含まれているトランザクション セットの数が一致しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93d2f51abc20f9cb790d2e6df62443f428c03dc8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970107"
---
# <a name="number-of-included-transaction-sets-do-not-match"></a>含まれているトランザクション セットの数が一致しません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                           X12FaNumberOfTsMismatchDescription                           |
|  メッセージ テキスト   |                    含まれているトランザクション セットの数が一致しません                    |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、X12 インターチェンジのグループのトランザクション セット数が、グループ トレーラー (GE01 フィールド) の数と等しくないことを示します。 これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。 (インターチェンジが保存され、トランザクション セットがエラーで中断している場合、またはインターチェンジが分割されている場合、エラー メッセージは通知されません)。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、グループ トレーラーの GE01 フィールドの数が、インターチェンジのグループのトランザクション セット数と同じであることを確認し、インターチェンジを再送信します。