---
title: シングル サインオン:イベント 10574 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f2a5aa-3a19-4d7c-9257-89f1567a3c2d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae5f0ecae1e9c3016817d1627ad0bfba75ef7ba4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398720"
---
# <a name="single-sign-on-event-10574"></a>シングル サインオン:イベント 10574
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                        エンタープライズ シングル サインオン                                                                         |
| 製品バージョン |                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                        |
|    イベント ID     |                                                                                  10574                                                                                   |
|  イベント ソース   |                                                                                  ENTSSO                                                                                  |
|    コンポーネント    |                                                                                   なし                                                                                    |
|  シンボル名  |                                                                     SSO_WARN_INVALID_SSO_ADMIN_GROUP                                                                     |
|  メッセージ テキスト   | SSO 管理者アカウントがグローバル情報 update.%r のため無効です。<br /><br /> SSO 管理者: % 1 %r<br /><br /> 無効なアカウント: % 2 %r<br /><br /> エラー コード: %3 |
  
## <a name="explanation"></a>説明  
 グローバル情報アダプターに対して、SSO 管理者アカウントが正しくありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告メッセージには、SSO 管理者アカウントおよび無効なアカウントに関する情報が含まれています。 この情報を確認、必要な修正、および更新プログラムをもう一度やり直してください。