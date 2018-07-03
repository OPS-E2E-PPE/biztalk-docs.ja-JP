---
title: 'シングル サインオン: イベント 10614 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1f9cd21-3f4b-446f-a4c7-15266973adf1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6cae7c64b5eeff339499f279aa85917211cbba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968171"
---
# <a name="single-sign-on-event-10614"></a>シングル サインオン: イベント 10614
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                        エンタープライズ シングル サインオン                                                                                                        |
| 製品バージョン |                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                        |
|    イベント ID     |                                                                                                                  10614                                                                                                                  |
|  イベント ソース   |                                                                                                                 ENTSSO                                                                                                                  |
|    コンポーネント    |                                                                                                                   なし                                                                                                                   |
|  シンボル名  |                                                                                                     SSO_WARN_INVALID_TICKET_TIMEOUT                                                                                                     |
|  メッセージ テキスト   | チケットのタイムアウト値がグローバル情報アダプターに対して無効です。%r<br /><br /> チケットのタイムアウト: %1 分 %r<br /><br /> 最小のチケットのタイムアウト: 1 分 %r<br /><br /> 最大のチケットのタイムアウト: %2 分 %r<br /><br /> エラー コード: %3 |
  
## <a name="explanation"></a>説明  
 指定されたチケットのタイムアウト値が無効です。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告メッセージで示されている情報を使用して、値を修正します。