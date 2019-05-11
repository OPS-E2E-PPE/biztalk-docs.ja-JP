---
title: シングル サインオン:イベント 10597 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c57db8f-f7e4-4745-89b6-3112a3b2e1be
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a65e16c4575b1eee29fd920ab55a3bf76bf87197
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397829"
---
# <a name="single-sign-on-event-10597"></a>シングル サインオン:イベント 10597
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                  エンタープライズ シングル サインオン                                                                                   |
| 製品バージョン |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    イベント ID     |                                                                                            10597                                                                                             |
|  イベント ソース   |                                                                                            ENTSSO                                                                                            |
|    コンポーネント    |                                                                                             なし                                                                                              |
|  シンボル名  |                                                                             SSO_WARN_CALLER_NOT_IN_NEW_SSO_ADMIN                                                                             |
|  メッセージ テキスト   | クライアント ユーザーは SSO 管理者アカウントの name.%r を変更するには、新しい SSO 管理者アカウントのメンバーである必要があります。<br /><br /> クライアント ユーザー: 1 %r<br /><br /> 新しい SSO 管理者: %2 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーは SSO 管理者アカウント名を変更するには、新しい SSO 管理者アカウントのメンバーである必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 SSO 管理者アカウント名を変更するには、新しい SSO 管理者アカウントのメンバーがあります。