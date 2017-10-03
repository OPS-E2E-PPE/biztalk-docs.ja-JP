---
title: "シングル サインオン: イベント 10708 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63675191-41cb-43fc-9355-e4ddc3f354c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d600c39b2e79e619e5adfbda2ffc152169ccd5d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10708"></a>シングル サインオン: イベント 10708
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10708|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_NO_WIN_SYNC|  
|メッセージ テキスト|Windows からのパスワード同期は許可されていません。 グローバル フラグを確認してください。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、パスワード同期が Windows によって要求され、どのグローバル フラグも設定されていないことを示します。 いずれかの外部システムへのパスワードの送信を許可する 2 つのフラグ: する SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB の外部システムからパスワードの受信を許可する SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL で、もうです。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   SSO 管理 MMC スナップインで、(システム (&) #124; を使用します。プロパティ & #124 です。オプション) またはコマンド ライン ツール`ssomanage –enable winsync/extsync`グローバル フラグを有効にします。  
  
## <a name="more-info"></a>詳細
  
-   **エンタープライズ シングル サインオン フラグ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)