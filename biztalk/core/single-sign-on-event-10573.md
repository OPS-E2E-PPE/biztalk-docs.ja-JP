---
title: 'シングル サインオン: イベント 10573 |Microsoft Docs'
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
ms.openlocfilehash: bf7b2dffb5bd78a3257a400cf2d3cb93978e1d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980185"
---
# <a name="single-sign-on-event-10573"></a>シングル サインオン: イベント 10573
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                  エンタープライズ シングル サインオン                                                                                   |
| 製品バージョン |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    イベント ID     |                                                                                            10573                                                                                             |
|  イベント ソース   |                                                                                            ENTSSO                                                                                            |
|    コンポーネント    |                                                                                             なし                                                                                              |
|  シンボル名  |                                                                             SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP                                                                             |
|  メッセージ テキスト   | SSO 関連管理者アカウントがグローバル情報アダプターに対して無効です。%r<br /><br /> SSO 関連管理者: % 1 %r<br /><br /> 無効なアカウント: % 2 %r<br /><br /> エラー コード: %3 |
  
## <a name="explanation"></a>説明  
 SSO 関連管理者アカウントがグローバル情報アダプターに対して無効です。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告メッセージには、SSO 関連管理者アカウントおよび無効なアカウントに関する情報が含まれます。 この情報を確認し、必要に応じて修正を行い、もう一度更新を試行します。