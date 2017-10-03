---
title: "シングル サインオン: イベント 10652 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62066b2fbbc47d07fa57f047313ed5ed8cda47d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10652"></a>シングル サインオン: イベント 10652
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10652|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_PASSWORD_SYNC_START_FAILED|  
|メッセージ テキスト|パスワード同期サービスを初期化できませんでした。%r<br /><br /> エラー コード: %1|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、例外が発生したためにパスワード同期サービスを開始できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   ENTSSO または他のサービスからの関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [パスワード同期](../core/password-synchronization2.md)