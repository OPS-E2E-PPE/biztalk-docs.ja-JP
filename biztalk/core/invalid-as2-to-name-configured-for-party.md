---
title: 無効な AS2 の名前がパーティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a203e5f2-d1d9-433f-b2bb-d679bb8fea58
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fdf3f4c307d8985df7e79ca1b8b45c569b76966
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381450"
---
# <a name="invalid-as2-to-name-configured-for-party"></a>無効な AS2-名前のパーティ用に構成するには
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                            InvalidAS2ToNameConfiguredError                             |
|  メッセージ テキスト   |               無効な AS2-名前のパーティ用に構成します。{0}   値: {1}               |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 エンコーダーまたはデコーダーために処理できませんでした、AS2 メッセージを示します、AS2 の値のヘッダーが AS2 RFC 4130 の仕様に準拠していなかった、識別されたパーティ用に構成します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決することを確認、AS2 のヘッダーが AS2 RFC 4130 のセクション 6.2 の仕様に準拠しているパーティ用に構成します。