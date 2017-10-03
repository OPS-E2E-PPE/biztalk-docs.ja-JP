---
title: "シングル サインオン: イベント 10557 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc65dba8760c85ad9eb6552e56e52cc6b7dd3ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10557"></a>シングル サインオン: イベント 10557
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10557|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS|  
|メッセージ テキスト|アプリケーション ユーザーはグループ アプリケーションのマッピングの制御を許可されていません。%r<br /><br /> ドメイン名: %1 %r<br /><br /> ユーザー名: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> クライアント ユーザー: %4|  
  
## <a name="explanation"></a>説明  
 アプリケーション ユーザーには、グループ アプリケーションのマッピングを作成または制御するのに十分な特権がありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このアクティビティはアプリケーション管理者が実行する必要があります。