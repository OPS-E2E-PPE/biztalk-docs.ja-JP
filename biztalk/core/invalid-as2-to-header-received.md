---
title: 無効な AS2-To 受信ヘッダー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56cd16b3-511b-4716-8806-817f174f0b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9acfbb11edabc26d1a01d36e545820892c65139
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330925"
---
# <a name="invalid-as2-to-header-received"></a>無効な AS2 のヘッダーを受信しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                          InvalidAS2ToNameHeaderReceivedError                           |
|  メッセージ テキスト   |                      無効な AS2 のヘッダーを受信しました。  値: {0}                       |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、エントリのため、受信パイプラインが受信インターチェンジが処理しないことを示します、AS2 の値-メッセージのメッセージ ヘッダーに準拠していなかった AS2 RFC 4130 の仕様にします。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決することを確認します、AS2 の値に、メッセージのヘッダーには、AS2 RFC 4130 のセクション 6.2 の仕様に準拠しています。