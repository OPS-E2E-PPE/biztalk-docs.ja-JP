---
title: TA1 インターチェンジに含まれる次のエラーが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6ce98988b8e52b808a5deaa9a8199bb37deb85e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254342"
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a>TA1 インターチェンジに含まれる次のエラーが
## <a name="details"></a>詳細  
  
|                 |                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------|
|  製品名   |                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| 製品バージョン |                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    イベント ID     |                                                        -                                                         |
|  イベント ソース   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI              |
|    コンポーネント    |                                                    EDI エンジン                                                    |
|  シンボル名  |                                                   X12TA1Error                                                    |
|  メッセージ テキスト   | {0} Id を持つインターチェンジに含まれている TA1 '{1}'、送信者 id'{2}'、受信者 id '{3}' 次のエラーが発生しました。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、受信パイプラインが表示されているエラー状態のため受信 TA1 受信確認を処理できなかったことを示します。 受信確認が TA1Schema に準拠していない可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、受信確認が、TA1Schema に準拠していることを確認、受信確認で問題を解決して、受信確認を再送信して、受信確認の送信者を依頼します。