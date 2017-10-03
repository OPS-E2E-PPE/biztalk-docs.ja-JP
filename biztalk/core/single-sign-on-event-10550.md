---
title: "シングル サインオン: イベント 10550 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73d63bc5-1e60-426c-a0d6-55c51dbb8d76
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9772885746f2c0519cba84db9ad1bee612607117
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10550"></a>シングル サインオン: イベント 10550
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10550|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_SERVICE_NOT_SSO_ADMIN|  
|メッセージ テキスト|SSO サービスを実行するサービス アカウントが SSO 管理者アカウントのメンバーではないため、SSO サービスを開始できませんでした。%r<br /><br /> SSO 管理者: %1 %r<br /><br /> SSO サービス アカウント: %2|  
  
## <a name="explanation"></a>説明  
 SSO サービスは、SSO 管理者アカウントのメンバーであるサービス アカウントで実行する必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 詳細については、次を参照してください。[ハウツー SSO 管理者の指定および関連管理者アカウント](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)です。