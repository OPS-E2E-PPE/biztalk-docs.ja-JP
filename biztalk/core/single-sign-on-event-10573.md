---
title: シングル サインオン:イベント 10573 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de1ea4e3-5d5f-4d50-8f9a-eff270ac0edb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37199e0b619f6d9f9d5a37ef1a6b4eb53c6f5712
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398729"
---
# <a name="single-sign-on-event-10573"></a>シングル サインオン:イベント 10573
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                  エンタープライズ シングル サインオン                                                                                   |
| 製品バージョン |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    イベント ID     |                                                                                            10573                                                                                             |
|  イベント ソース   |                                                                                            ENTSSO                                                                                            |
|    コンポーネント    |                                                                                             なし                                                                                              |
|  シンボル名  |                                                                             SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP                                                                             |
|  メッセージ テキスト   | SSO 関連管理者アカウントがグローバル情報 update.%r のため無効です。<br /><br /> SSO 関連管理者: % 1 %r<br /><br /> 無効なアカウント: % 2 %r<br /><br /> エラー コード: %3 |
  
## <a name="explanation"></a>説明  
 SSO 関連管理者アカウントがグローバル情報アダプターに対して有効ではありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告メッセージには、SSO 関連管理者アカウントおよび無効なアカウントに関する情報が含まれています。 この情報を確認、必要な修正、および更新プログラムをもう一度やり直してください。