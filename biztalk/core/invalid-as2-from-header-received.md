---
title: 無効な AS2 のヘッダーを受信しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d773e09-8526-4533-9066-8e743e65a688
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 935995719473c8ff7977b47ec8b6971229b1a795
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381424"
---
# <a name="invalid-as2-from-header-received"></a>無効な AS2 のヘッダーを受信しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                         InvalidAS2FromNameHeaderReceivedError                          |
|  メッセージ テキスト   |                     無効な AS2 のヘッダーを受信しました。  値: {0}                      |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、エントリのため、受信パイプラインが受信インターチェンジが処理しないことを示します、AS2 の値-メッセージのメッセージ ヘッダーから準拠していなかった AS2 RFC 4130 の仕様にします。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決することを確認、AS2 の値-メッセージのヘッダーから、AS2 RFC 4130 のセクション 6.2 の仕様に準拠し、メッセージを再送信します。