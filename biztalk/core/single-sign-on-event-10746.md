---
title: "シングル サインオン: イベント 10746 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc2bc096211d8a90089b3b5fdd31b4dbb82f2b14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10746"></a>シングル サインオン: イベント 10746
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10746|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PASSWORD_EXPIRED|  
|メッセージ テキスト|外部アカウントのパスワードの有効期限が切れています。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> 外部アカウント: %3|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、外部アカウントのパスワードの有効期限が切れていることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、関連付けられているエラーのシステムとアプリケーション イベント ログを確認します。    

## <a name="more-info"></a>詳細
詳細については、次のリソースを参照してください。  
  
-   **パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
  
-   [パスワード同期](../core/password-synchronization2.md)