---
title: シングル サインオン:イベント 10614 |Microsoft Docs
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
ms.openlocfilehash: a5fc2758327087d0b312de16b6f7c8ebc6b5bb6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397693"
---
# <a name="single-sign-on-event-10614"></a>シングル サインオン:イベント 10614
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                        エンタープライズ シングル サインオン                                                                                                        |
| 製品バージョン |                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                        |
|    イベント ID     |                                                                                                                  10614                                                                                                                  |
|  イベント ソース   |                                                                                                                 ENTSSO                                                                                                                  |
|    コンポーネント    |                                                                                                                   なし                                                                                                                   |
|  シンボル名  |                                                                                                     SSO_WARN_INVALID_TICKET_TIMEOUT                                                                                                     |
|  メッセージ テキスト   | チケットのタイムアウト値がグローバル情報 update.%r のため無効です。<br /><br /> チケットのタイムアウト: %1 分 %r<br /><br /> 最小のチケットのタイムアウト:1 分 %r<br /><br /> 最大のチケットのタイムアウト: %2 分 %r<br /><br /> エラー コード: %3 |
  
## <a name="explanation"></a>説明  
 指定したチケットのタイムアウト値が無効です。  
  
## <a name="user-action"></a>ユーザーの操作  
 値を修正するのにには、警告メッセージで指定された情報を使用します。