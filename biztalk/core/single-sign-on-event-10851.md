---
title: 'シングル サインオン: イベント 10851 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15121c1d7829f04bd9c106ed71da391d401ae564
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987235"
---
# <a name="single-sign-on-event-10851"></a>シングル サインオン: イベント 10851
## <a name="details"></a>詳細  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                             エンタープライズ シングル サインオン                                             |
| 製品バージョン |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    イベント ID     |                                                       10851                                                       |
|  イベント ソース   |                                                      ENTSSO                                                       |
|    コンポーネント    |                                                        なし                                                        |
|  シンボル名  |                                     ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC                                      |
|  メッセージ テキスト   | '直接パスワード同期' フラグが設定されているので、アプリケーションをパスワード同期アダプターに割り当てることができません。 |
  
## <a name="explanation"></a>説明  
 アプリケーションでは、直接パスワード同期とパスワード同期アダプターの両方を使用することはできません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アプリケーションを見直して、直接パスワード同期が必要であるかどうかを決定します。必要である場合は、このフラグを設定したままにして、アプリケーションをパスワード同期アダプターに割り当てないようにします。 必要ではない場合は、このフラグをオフにし、必要に応じてアプリケーションをパスワード同期アダプターに割り当てます。