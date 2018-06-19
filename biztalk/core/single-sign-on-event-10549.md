---
title: 'シングル サインオン: イベント 10549 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a59feecdcf5daeef7013dd99eca1e778d49278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270466"
---
# <a name="single-sign-on-event-10549"></a>シングル サインオン: イベント 10549
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10549|  
|イベント ソース|ENTSSO|  
|コンポーネント|CO|  
|シンボル名|SSO_ERROR_CREATE_DATABASE_FAILED|  
|メッセージ テキスト|SSO データベースを作成および初期化できませんでした。%r<br /><br /> SQL Server 名: %1 %r<br /><br /> SSO データベース名: %2 %r<br /><br /> クライアント ユーザー: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 このエラーは、SSO データベースを作成および初期化できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います:   
  
-   システムおよびアプリケーションのイベント ログで関連するメッセージを確認します。  
  
-   セットアップを再実行します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO のインストール](../core/installing-sso.md)