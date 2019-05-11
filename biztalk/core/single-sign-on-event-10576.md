---
title: シングル サインオン:イベント 10576 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b2d9904-4302-41b7-bced-7db46cc05d7f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8492d2d6e9aee841d60aea305dc6669f7df63efe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303472"
---
# <a name="single-sign-on-event-10576"></a>シングル サインオン:イベント 10576
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                              エンタープライズ シングル サインオン                                                                                              |
| 製品バージョン |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    イベント ID     |                                                                                                        10576                                                                                                        |
|  イベント ソース   |                                                                                                       ENTSSO                                                                                                        |
|    コンポーネント    |                                                                                                         なし                                                                                                         |
|  シンボル名  |                                                                                             SSO_INFO_CHANGED_SSO_ADMIN                                                                                              |
|  メッセージ テキスト   | SSO の更新の管理者 account.%r<br /><br /> 新しい SSO 管理者: % 1 %r<br /><br /> 古い SSO 管理者: % 2 %r<br /><br /> 追跡 ID: % 3 %r<br /><br /> クライアント コンピューターの場合: % 4 %r<br /><br /> クライアント ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 これは、情報メッセージであり、SSO システム内でその発生の重要なセキュリティ関連イベントを追跡するために便利です。 このメッセージは、SSO 管理者アカウントが更新されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーによる操作は不要です。