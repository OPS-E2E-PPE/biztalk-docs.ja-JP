---
title: 無効な AS2 の名前がパーティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde739bd-f6f7-4e4a-8f02-9a99e9d82fc9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4db0fe98bcb04f662e4a827f4139e0cff81275
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331041"
---
# <a name="invalid-as2-from-name-configured-for-party"></a>無効な AS2 の名前がパーティの構成
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                           InvalidAS2FromNameConfiguredError                            |
|  メッセージ テキスト   |              無効な AS2、パーティ用に構成された名前から。{0}   値: {1}              |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 エンコーダーまたはデコーダーために処理できませんでした、AS2 メッセージを示します、AS2 の値のヘッダーが AS2 RFC 4130 の仕様に準拠していなかった、識別されたパーティ用に構成されたからです。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決することを確認します、AS2、パーティが AS2 RFC 4130 のセクション 6.2 の仕様に準拠しているし、メッセージを再送信用に構成されたヘッダー。