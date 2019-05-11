---
title: トランザクション セット制御番号シーケンスがパートナーと TPA の |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89f917dc3688755816c29dea82ae153133dcca05
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279708"
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a>トランザクション セット制御番号シーケンスがパートナーと TPA の
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| 製品バージョン |                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                       |
|    イベント ID     |                                                                                   -                                                                                    |
|  イベント ソース   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                         |
|    コンポーネント    |                                                                               EDI エンジン                                                                               |
|  シンボル名  |                                                                   EdiControlNumberExhaustedForParty                                                                    |
|  メッセージ テキスト   | トランザクション セット制御番号シーケンスがパートナー '{1}'for 'TPA{2}'。 シーケンスをリセット{2}- BizTalk Server 管理コンソールを使用して EDI のプロパティ。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server がドキュメントのため、トランザクション セット制御の範囲が使用されたアグリーメントに処理することを示します{2}します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、制御番号をリセットするチェック ボックスをオンしてください、{2}契約または増加コントロール番号の範囲または契約書に制御番号の範囲指定に対するリセット ボタンをクリックします。