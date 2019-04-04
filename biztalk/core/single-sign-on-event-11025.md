---
title: 'シングル サインオン: イベント 11025 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df5a733b-3c95-409c-8485-bf3f7feb3c50
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd8c25dc80669b4524c7e9ce848e4b0e28f773f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015899"
---
# <a name="single-sign-on-event-11025"></a>シングル サインオン: イベント 11025
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                 エンタープライズ シングル サインオン                                                                                                  |
| 製品バージョン |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                 |
|    イベント ID     |                                                                                                           11025                                                                                                            |
|  イベント ソース   |                                                                                                           ENTSSO                                                                                                           |
|    コンポーネント    |                                                                                                            なし                                                                                                             |
|  シンボル名  |                                                                                            SSO_WARN_INVALID_APP_TICKET_TIMEOUT                                                                                             |
|  メッセージ テキスト   | チケットのタイムアウト値がアプリケーション アダプターに対して無効です。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> チケットのタイムアウト: %2 分 %r<br /><br /> 最大のチケットのタイムアウト: %3 分 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 チケットのタイムアウト値が無効です。  
  
## <a name="user-action"></a>ユーザーの操作  
 チケットのタイムアウトの詳細については、[SSO 関連アプリケーション](../core/sso-affiliate-applications.md)を参照してください。