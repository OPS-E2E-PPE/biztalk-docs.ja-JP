---
title: "シングル サインオン: イベント 10735 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c791c6-1901-4441-b329-ed75833cb83e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94417860296cf01c2266a678832f8b02b9b51055
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10735"></a>シングル サインオン: イベント 10735
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10735|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_APP_DISABLED|  
|メッセージ テキスト|外部パスワードが変更されています。 アプリケーションが無効になっているため、外部アカウントのパスワードは変更されませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> 外部アカウント: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーションが無効になっているため、外部アカウントのパスワードが変更されなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   関連アプリケーションを有効にします。  
  
 詳細については、次のリソースを参照してください。  
  
-   [関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)  
  
-   [パスワード同期](../core/password-synchronization2.md)