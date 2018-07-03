---
title: 'シングル サインオン: イベント 10612 |Microsoft Docs'
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
ms.openlocfilehash: 3fdc86dd2143bf8b2b4c27dab66cc4c06ddff5ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973019"
---
# <a name="single-sign-on-event-10612"></a>シングル サインオン: イベント 10612
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                            エンタープライズ シングル サインオン                                                                                                                            |
| 製品バージョン |                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    イベント ID     |                                                                                                                                      10612                                                                                                                                      |
|  イベント ソース   |                                                                                                                                     ENTSSO                                                                                                                                      |
|    コンポーネント    |                                                                                                                                       なし                                                                                                                                       |
|  シンボル名  |                                                                                                                          SSO_WARN_TRANSACTION_TIMEOUT                                                                                                                           |
|  メッセージ テキスト   | トランザクションのタイムアウト値が、この操作で推奨される最大値を超えています。 Details.%r のドキュメントを参照してください。<br /><br /> トランザクション ID: %1 %r<br /><br /> トランザクションのタイムアウト: %2 分 (0 には、無限のタイムアウトことを示します) %r<br /><br /> 推奨される最大値: %3 分 |
  
## <a name="explanation"></a>説明  
 非常に大きなタイムアウト値が設定されたトランザクションがシステムで処理されています。 実行時間の長いトランザクションによってロックされているときに ENTSSO システムが SSO データベースをポーリングした場合、システムは最終的にはオフラインになります。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーによる操作は不要です。