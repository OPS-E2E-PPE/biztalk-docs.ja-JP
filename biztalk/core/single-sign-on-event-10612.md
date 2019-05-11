---
title: シングル サインオン:イベント 10612 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b73a601e883f651b5333224c557a1344d32943c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397712"
---
# <a name="single-sign-on-event-10612"></a>シングル サインオン:イベント 10612
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                            エンタープライズ シングル サインオン                                                                                                                            |
| 製品バージョン |                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    イベント ID     |                                                                                                                                      10612                                                                                                                                      |
|  イベント ソース   |                                                                                                                                     ENTSSO                                                                                                                                      |
|    コンポーネント    |                                                                                                                                       なし                                                                                                                                       |
|  シンボル名  |                                                                                                                          SSO_WARN_TRANSACTION_TIMEOUT                                                                                                                           |
|  メッセージ テキスト   | トランザクションのタイムアウトは、この操作に推奨される最大値を超えています。 Details.%r のドキュメントを参照してください。<br /><br /> トランザクション ID: %1 %r<br /><br /> トランザクションのタイムアウト: %2 分 (0 には、無限のタイムアウトことを示します) %r<br /><br /> 推奨される最大値: %3 分 |
  
## <a name="explanation"></a>説明  
 トランザクションには、非常に大きなタイムアウト値を持つシステムが入力されます。 場合は、ENTSSO システムは、実行時間の長いトランザクションによってロックされている SSO データベースをポーリングし、システムは最終的にオフラインになります。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーによる操作は不要です。